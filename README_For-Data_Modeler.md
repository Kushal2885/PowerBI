This model follows Star Schema design where Sales_Fact is central table connected to dimension tables like Customer, Product, Region and Date.
Returns_Fact is modeled as a secondary fact table connected to Sales_Fact.

All relationships follow Many-to-One cardinality with Single Direction filtering to maintain performance and avoid ambiguity.
Inactive relationship is created between Returns_Fact and Date_Dim using ReturnDateKey.

Filter ambiguity could occur due to multiple paths between Date and Returns.
This was resolved by keeping ReturnDateKey relationship inactive.
