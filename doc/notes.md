# Custom blocks
## Block creation
- `ManSpawn.AddBlocksToTech` uses `m_BlockAliasing` to translate obsolete `BlockTypes` values to new ones.
- `ManSpawn.SpawnBlock` uses `m_BlockPrefabs` to create new block instances.

## Block shop population
- Block shop: `UIShopBlockSelect`
- Available blocks are shown by `UIBlockSelectGrid`, which uses `ManLicense` to determine the blocks that are available.
- The list for all known blocks in the shop originates from `ManLicenses.GetAllBlocksForFaction(FactionSubTypes)`.

## Attachment points
- `TankBlock.attachPoints` is a `Vector3[]` containing the points the block can be connected on.

## GameObject graph
The following graph has been generated by calling `Mod.LogGameObject(GameObject)` from `ManSpawn.AddBlockToDictionary()`. It displays the GameObject graph of the prefab used to create standard GSO 1x1x1 blocks. The list after `TankBlock` contains the `Vector3` of `TankBlock.attachPoints`.
```
GameObject: GSOBlock(111) (0.0, 0.0, 0.0)
	Component: UnityEngine.Transform 
	Component: TankBlock 
	  - (0.5, 0.0, 0.0)
	  - (0.0, 0.0, -0.5)
	  - (0.0, 0.0, 0.5)
	  - (-0.5, 0.0, 0.0)
	  - (0.0, -0.5, 0.0)
	  - (0.0, 0.5, 0.0)
	Component: Visible Bitfield`1[Visible+StateFlags]
	Component: AutoSpriteRenderer 
	Component: ModuleDamage 
	Component: Damageable 
	GameObject: GSO_Block_111 (0.0, 0.0, 0.0)
		Component: UnityEngine.Transform 
		Component: UnityEngine.MeshFilter m_GSO_Block_111 Instance
		Component: UnityEngine.MeshRenderer 
		Component: UnityEngine.BoxCollider (0.0, 0.0, 0.0) (1.0, 1.0, 1.0)
		GameObject: m_GSO_Block_111_APs (0.0, 0.0, 0.0)
			Component: UnityEngine.Transform 
			Component: UnityEngine.MeshFilter m_GSO_Block_111_APs Instance
			Component: UnityEngine.MeshRenderer 
```