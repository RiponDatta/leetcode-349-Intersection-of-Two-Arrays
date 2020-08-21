# leetcode 349 - Intersection of Two Arrays

## Java
```Java
```

## C#
```C#
public static int[] Intersection(int[] nums1, int[] nums2)
{
    var result = new List<int>();
    var ht = new Hashtable();
    for (int i = 0; i < nums1.Length; i++)
    {
        if (!ht.Contains(nums1[i]))
            ht.Add(nums1[i], 1);
    }
    for (int i = 0; i < nums2.Length; i++)
    {
        if (ht.Count == 0) break;
        if (ht.Contains(nums2[i]))
        {
            result.Add(nums2[i]);
            ht.Remove(nums2[i]);
        }
    }
    var ret = new int[result.Count];
    for (int i = 0; i < result.Count; i++)
        ret[i] = result[i];
    return ret;
}
```
