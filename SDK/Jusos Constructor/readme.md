# .loaded
- Load Objects from a known Package and keep it loaded
- First files to be processed, should be good using them in your regular "set"
##
- -- "#SanctuaryAir_Dynamic"
- '#' means: load package 'SanctuaryAir_Dynamic', in python it is 'unrealsdk.LoadPackage("SanctuaryAir_Dynamic")'
##
- -- "FX_ENV_Misc.Particles.Part_Confetti"
- Read as an Object and the sdk will try to keep it loaded, in Python it is 'unrealsdk.KeepAlive(unrealsdk.FindObject("Object", "FX_ENV_Misc.Particles.Part_Confetti"))'
##
- -- "#GD_Mercenary_Streaming_SF"
- -- "D_Attributes.DamageEnhancementModifiers.LastShotInClipBonusModifier"
- Includes any package, load object for universal use.
##Resume
```
#Package
D_Object.Ingame.replacethis
```
---
# .construct
- Avoid to manually construct every object, maintains the games integrity while adding your newly created objects.
##
- For a completely new gun we want to start with it's "WeaponBalanceDefinition"
- The "#" is used to determine the class which our to be cloned object is an instance of.
- --- "#WeaponBalanceDefinition"
##
- New object syntax: <object_template> [new object Name] [new object Outer]
- --- "GD_Weap_Shotgun.A_Weapons_Legendary.SG_Bandit_5_SledgesShotgun SG_Bandit_5_Confetti" [no outer needed]
- This constructs "WeaponBalanceDefinition'GD_Weap_Shotgun.A_Weapons_Legendary.SG_Bandit_5_Confetti'"
##
- --- "#WeaponPartDefinition"
- --- "GD_Weap_Shotgun.Barrel.SG_Barrel_Jakobs_Sledges SG_Barrel_Confetti"
- This constructs "WeaponPartDefinition'GD_Weap_Shotgun.Barrel.SG_Barrel_Confetti'"
##
- For the material, to add a skin later
- --- "GD_Weap_Shotgun.ManufacturerMaterials.Mat_Bandit_5_Legendary Mat_Bandit_5_Legendary_Confetti"
##
- Firing Mode
- --- "#FiringModeDefinition"
- --- "GD_Weap_Shotgun.FiringModes.Bullet_Shotgun_Teeth Bullet_Shotgun_Confetti"
##
- Title
- --- "#WeaponNamePartDefinition"
- --- "GD_Weap_Shotgun.Name.Title_Bandit.Title_Legendary_Shotgun Title_Legendary_Confetti"
##
- All elements constructed.
- Automatic "GD_Weap_Shotgun.A_Weapons_Legendary.SG_Bandit_5_Confetti:WeaponPartListCollectionDefinition_1000" constructed and assigned to it.
##
## Resume
```
#WeaponBalanceDefinition
GD_Weap_Shotgun.A_Weapons_Legendary.SG_Bandit_5_SledgesShotgun SG_Bandit_5_Confetti
#WeaponPartDefinition
GD_Weap_Shotgun.Barrel.SG_Barrel_Jakobs_Sledges SG_Barrel_Confetti
GD_Weap_Shotgun.ManufacturerMaterials.Mat_Bandit_5_Legendary Mat_Bandit_5_Legendary_Confetti
#FiringModeDefinition
GD_Weap_Shotgun.FiringModes.Bullet_Shotgun_Teeth Bullet_Shotgun_Confetti
#WeaponNamePartDefinition
GD_Weap_Shotgun.Name.Title_Bandit.Title_Legendary_Shotgun Title_Legendary_Confetti
```
#### Includes bdp as well
```
#BehaviorProviderDefinition
GD_Mercenary_Skills.Gun_Lust.LockedandLoaded:BehaviorProviderDefinition_10 BehaviorProviderDefinition_10 GD_Tulip_Mechromancer_Skills.LittleBigTrouble.ShockAndAAAGGGHHH
```
#### blcmm
```
set GD_Tulip_Mechromancer_Skills.LittleBigTrouble.ShockAndAAAGGGHHH BehaviorProviderDefinition BehaviorProviderDefinition'GD_Tulip_Mechromancer_Skills.LittleBigTrouble.ShockAndAAAGGGHHH:BehaviorProviderDefinition_10'
```
---
# To BLCMM
#### Partlist
```
set GD_Weap_Shotgun.A_Weapons_Legendary.SG_Bandit_5_Confetti:WeaponPartListCollectionDefinition_1000 BarrelPartData (bEnabled = True,WeightedParts=((Part = WeaponPartDefinition'GD_Weap_Shotgun.Barrel.SG_Barrel_Confetti',Manufacturers = ,MinGameStageIndex = 0,MaxGameStageIndex = 1,DefaultWeightIndex = 1)))
set GD_Weap_Shotgun.A_Weapons_Legendary.SG_Bandit_5_Confetti:WeaponPartListCollectionDefinition_1000 MaterialPartData (bEnabled = True,WeightedParts =((Part = WeaponPartDefinition'GD_Weap_Shotgun.ManufacturerMaterials.Mat_Bandit_5_Legendary_Confetti',Manufacturers = ,MinGameStageIndex = 0,MaxGameStageIndex = 1,DefaultWeightIndex = 1)))
```
#### FiringMode
```
set GD_Weap_Shotgun.Barrel.SG_Barrel_Confetti CustomFiringModeDefinition FiringModeDefinition'GD_Weap_Shotgun.FiringModes.Bullet_Shotgun_Confetti'
set GD_Weap_Shotgun.FiringModes.Bullet_Shotgun_Confetti PartSysTemplate ParticleSystem'FX_ENV_Misc.Particles.Part_Confetti'
set GD_Weap_Shotgun.FiringModes.Bullet_Shotgun_Confetti:Behavior_Explode_0 DamageSource Class'WillowGame.WillowDmgSource_Melee
set GD_Weap_Shotgun.FiringModes.Bullet_Shotgun_Confetti:Behavior_Explode_0 DamageRadiusFormula (BaseValueConstant=10.000000,BaseValueAttribute=None,InitializationDefinition=None,BaseValueScaleConstant=1.000000)
set GD_Weap_Shotgun.FiringModes.Bullet_Shotgun_Confetti:Behavior_Explode_0 DamageFormula (BaseValueConstant=0.000000,BaseValueAttribute=AttributeDefinition'D_Attributes.Weapon.WeaponDamage',InitializationDefinition=None,BaseValueScaleConstant=1.000000)
```
#### Barrel
```
set GD_Weap_Shotgun.Barrel.SG_Barrel_Confetti PrefixList ()
set GD_Weap_Shotgun.Barrel.SG_Barrel_Confetti TitleList (WeaponNamePartDefinition'GD_Weap_Shotgun.Name.Title_Bandit.Title_Legendary_Confetti')
set GD_Weap_Shotgun.Barrel.SG_Barrel_Confetti GestaltModeSkeletalMeshName SG_Barrel_Torgue
set GD_Weap_Shotgun.Barrel.SG_Barrel_Confetti WeaponAttributeEffects ((AttributeToModify=AttributeDefinition'D_Attributes.Weapon.WeaponFireInterval',ModifierType=MT_Scale,BaseModifierValue=(BaseValueConstant=-1.250000,BaseValueAttribute=None,InitializationDefinition=None,BaseValueScaleConstant=1.000000)),(AttributeToModify=AttributeDefinition'D_Attributes.Weapon.WeaponReloadSpeed',ModifierType=MT_Scale,BaseModifierValue=(BaseValueConstant=-0.250000,BaseValueAttribute=None,InitializationDefinition=None,BaseValueScaleConstant=1.000000)),(AttributeToModify=AttributeDefinition'D_Attributes.Weapon.WeaponShotCost',ModifierType=MT_PreAdd,BaseModifierValue=(BaseValueConstant=0.000000,BaseValueAttribute=None,InitializationDefinition=None,BaseValueScaleConstant=1.000000)),(AttributeToModify=AttributeDefinition'D_Attributes.Weapon.WeaponProjectilesPerShot',ModifierType=MT_PreAdd,BaseModifierValue=(BaseValueConstant=-3.000000,BaseValueAttribute=None,InitializationDefinition=None,BaseValueScaleConstant=1.000000)),(AttributeToModify=AttributeDefinition'D_Attributes.Weapon.WeaponClipSize',ModifierType=MT_Scale,BaseModifierValue=(BaseValueConstant=0.000000,BaseValueAttribute=None,InitializationDefinition=None,BaseValueScaleConstant=1.000000)))
```
#### Name
```
set GD_Weap_Shotgun.Name.Title_Bandit.Title_Legendary_Confetti PartName Confetti
set GD_Weap_Shotgun.Name.Title_Bandit.Title_Legendary_Confetti:AttributePresentationDefinition_1000 NoConstraintText *Puff*
set GD_Weap_Shotgun.ManufacturerMaterials.Mat_Bandit_5_Legendary_Confetti WeaponCardAttributes ()
```
#### Rarity
```
set GD_Weap_Pistol.Barrel.Pistol_Barrel_XX_Masher rarity (BaseValueConstant = -1.000000,BaseValueAttribute = None,InitializationDefinition = None,BaseValueScaleConstant = 1.000000)
```
# .material
- Keep in mind to add the right Parent, the new MaterialInstanceConstant doesn't have any Parent Object, therefore wont show anything until you set its Parent.
```
set GD_Weap_Pistol.ManufacturerMaterials.Mat_Jakobs_5_Legendary_XX Parent MaterialInstanceConstant'Common_GunMaterials.Materials.Pistol.Mati_JakobsLegendaryPistol_Maggie'
set GD_Weap_Pistol.ManufacturerMaterials.Mat_Jakobs_5_Legendary_XX TextureParameterValues ((ParameterName="p_NormalScopesEmissive",ParameterValue=Texture2D'Weap_Pistol.Tex.Weap_Pistols_Nrm',ExpressionGUID=(A=-1743872746,B=1126171774,C=119496871,D=-1952271718)),(ParameterName="p_Diffuse",ParameterValue=Texture2D'Common_GunMaterials.CompTextures.Weap_LauncherShotgunPistol_Comp',ExpressionGUID=(A=1757607260,B=1326539502,C=-317215581,D=-565807463)),(ParameterName="p_Masks",ParameterValue=Texture2D'Weap_Pistol.Tex.Weap_Pistols_Comp',ExpressionGUID=(A=-330624041,B=1167251458,C=-335191907,D=-166684394)),(ParameterName="P_SimpleReflect",ParameterValue=Texture2D'Common_GunMaterials.Env.Gold',ExpressionGUID=(A=-858148940,B=1327945772,C=148462268,D=1899047224)),(ParameterName="p_Pattern",ParameterValue=Texture2D'Common_GunMaterials.Patterns.Pattern_JakobsEpic_SpaltedMaple',ExpressionGUID=(A=534250533,B=1202550002,C=1578302861,D=-717876416)),(ParameterName="p_Decal",ParameterValue=Texture2D'Common_GunMaterials.Logos.Logo_VladofColor',ExpressionGUID=(A=-923052711,B=1309861752,C=584229786,D=-1229888527)))
set GD_Weap_Pistol.ManufacturerMaterials.Mat_Jakobs_5_Legendary_XX VectorParameterValues ((ParameterName="p_AColorHilight",ParameterValue=(R=1.50000,G=0.15000,B=0.02500,A=1.000000),ExpressionGUID=(A=170014760,B=1132076783,C=-275608290,D=650702143)),(ParameterName="p_AColorMidtone",ParameterValue=(R=0.30000,G=0.03000,B=0.00500,A=1.000000),ExpressionGUID=(A=473504356,B=1338058895,C=824823046,D=864253013)),(ParameterName="p_AColorShadow",ParameterValue=(R=0.06000,G=0.00600,B=0.00100,A=1.000000),ExpressionGUID=(A=-429590041,B=1156405294,C=-1015192900,D=687313410)),(ParameterName="p_BColorHilight",ParameterValue=(R=0.200000,G=0.200000,B=0.600000,A=1.000000),ExpressionGUID=(A=170014760,B=1132076783,C=-275608290,D=650702143)),(ParameterName="p_BColorMidtone",ParameterValue=(R=0.040000,G=0.040000,B=0.120000,A=1.000000),ExpressionGUID=(A=473504356,B=1338058895,C=824823046,D=864253013)),(ParameterName="p_BColorShadow",ParameterValue=(R=0.008000,G=0.008000,B=0.024000,A=1.000000),ExpressionGUID=(A=-429590041,B=1156405294,C=-1015192900,D=687313410)),(ParameterName="p_CColorHilight",ParameterValue=(R=2.000000,G=1.000000,B=0.500000,A=1.000000),ExpressionGUID=(A=170014760,B=1132076783,C=-275608290,D=650702143)),(ParameterName="p_CColorMidtone",ParameterValue=(R=0.400000,G=0.200000,B=0.100000,A=1.000000),ExpressionGUID=(A=473504356,B=1338058895,C=824823046,D=864253013)),(ParameterName="p_CColorShadow",ParameterValue=(R=0.080000,G=0.040000,B=0.020000,A=1.000000),ExpressionGUID=(A=-429590041,B=1156405294,C=-1015192900,D=687313410)),(ParameterName="p_DColor",ParameterValue=(R=0.100000,G=0.100000,B=0.100000,A=1.000000),ExpressionGUID=(A=696455109,B=1155878830,C=-1741888361,D=802120528)),(ParameterName="p_EmissiveColor",ParameterValue=(R=0.000000,G=0.000000,B=0.000000,A=1.000000),ExpressionGUID=(A=-2074486426,B=1296399582,C=-2021314681,D=-350758005)),(ParameterName="p_ReflectColor",ParameterValue=(R=16.000000,G=16.000000,B=16.000000,A=1.000000),ExpressionGUID=(A=295058103,B=1318551573,C=-2045449573,D=-547597976)),(ParameterName="p_ReflectionChannelScale",ParameterValue=(R=0.000000,G=1.000000,B=1.000000,A=1.000000),ExpressionGUID=(A=295058103,B=1318551573,C=-2045449573,D=-547597976)),(ParameterName="p_PatternColor",ParameterValue=(R=1.000000,G=0.100000,B=0.100000,A=1.000000),ExpressionGUID=(A=676539706,B=1125682796,C=1871983293,D=-2049503601)),(ParameterName="p_PatternScalePosition",ParameterValue=(R=7.500000,G=7.500000,B=6.000000,A=1.000000),ExpressionGUID=(A=-2005018406,B=1132497243,C=-39915121,D=208423616)),(ParameterName="p_PatternChannelScale",ParameterValue=(R=1.000000,G=0.000000,B=0.000000,A=1.000000),ExpressionGUID=(A=439432319,B=1091149893,C=-1991909502,D=1816944627)),(ParameterName="p_DecalColor",ParameterValue=(R=6.000000,G=0.200000,B=0.200000,A=1.000000),ExpressionGUID=(A=1691998600,B=1239094551,C=2074257317,D=1844701893)),(ParameterName="p_DecalScalePosition",ParameterValue=(R=7.500000,G=7.500000,B=0.7050000,A=0.3800000),ExpressionGUID=(A=395540170,B=1243133493,C=-1264190552,D=123075385)),(ParameterName="p_DecalChannel",ParameterValue=(R=0.000000,G=0.000000,B=0.000000,A=1.000000),ExpressionGUID=(A=1869386622,B=1303200947,C=-1616405849,D=714558284)))
set GD_Weap_Pistol.ManufacturerMaterials.Mat_Jakobs_5_Legendary_XX ScalarParameterValues ((ParameterName="p_HighlightsIntensity",ParameterValue=0.450000,ExpressionGUID=(A=-1257568432,B=1277066486,C=-723473993,D=-1144384173)),(ParameterName="p_ShadowsIntensity",ParameterValue=1.000000,ExpressionGUID=(A=437293753,B=1205147708,C=-775723903,D=1480014964)),(ParameterName="p_ReflectColorScale",ParameterValue=1.000000,ExpressionGUID=(A=1875785607,B=1186033550,C=-1822263113,D=-1465755701)),(ParameterName="p_ReplacePattern",ParameterValue=1.00000,ExpressionGUID=(A=-2084339847,B=1096440125,C=439008937,D=45433490)),(ParameterName="p_DecalRotate",ParameterValue=0.200000,ExpressionGUID=(A=-276527909,B=1298581551,C=856978878,D=743944047)),(ParameterName="p_ReplaceDecal",ParameterValue=1.000000,ExpressionGUID=(A=85863466,B=1257609701,C=-728575820,D=1337098176)),(ParameterName="p_UseFullColorDecal",ParameterValue=1.000000,ExpressionGUID=(A=-1064329812,B=1077705328,C=339664807,D=1869745420)))
```
# .itempool
- "/" is similar to hotfixes on map load
- "/mappackage" means that the following code will only be executed if the mappackage got loaded
- "/None" means on any map load
### Example:
```
/None
'#GD_Itempools.EarlyGame.Pool_Knuckledragger_Chest_Shotgun
ItemPoolDefinition None
InvBalanceDefinition GD_Weap_Pistol.A_Weapons_Legendary.Pistol_Jakobs_5_XX
BaseValueConstant 0.000000
BaseValueAttribute None
InitializationDefinition AttributeInitializationDefinition'GD_Balance.Weighting.Weight_1_Common'
BaseValueScaleConstant 1.000000
bDropOnDeath True
+
```
#### With love, Lupci
