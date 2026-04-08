---
title: "Binary Serialization"
icon: "🔟"
created: 2026-01-16
updated: 2026-01-16
---

# Binary Serialization

In the event that you find your JSON files growing too much due to too much data. You can store data as a binary blob. This will work with anything that serializes to JSON.

## Creating a binary blob

Here's a snippet with a game resource that stores a list of positions in a companion binary blob while the rest is in clear JSON.

```csharp
// Custom Asset that will serialize MyBinaryBlob as binary data
[AssetType( Name = "My CustomResource", Extension = "res", Category = "other" )]
public partial class CustomResource : GameResource
{
	public string Title { get; set; }

	public MyBigData Data = new();
}

// This will be stored as binary data according to Serialize & Deserialize method
public class MyBigData : BinarySerializable
{
    public List<float> Data { get; set; } = [];
    
    public void override Serialize( ref BlobWriter writer )
    {
        // This layout will be what we will be deserializing, plan accordingly
        
        writer.Write( Data.Count ); // Int
        
        foreach ( var instance in Data ) // float * Data.Count
        {
            writer.Write( instance );
        }
    }
    
    public void override Deserialize( ref BlobReader )
    {
        var instanceCount = reader.Read<int>(); // Int
        
        for( int i = 0; i < instanceCount; i++ )
        {
            Data.Add( reader.Stream.Read<float>() );
        }
    }
}
```

## Considerations

Working with binary files requires a bit more planning as it is not human readable. For example, deserializing a dynamic list is done by writing the size first so that we know how many elements to skip or read. Just like in the example above.
