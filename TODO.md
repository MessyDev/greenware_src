# TODO for Updating Roblox LSP in source.lua

## 1. Change Color Theme to Green
- [x] Set Configuration.FoVColour to Color3.fromRGB(0, 255, 0)
- [x] Set Configuration.ESPColour to Color3.fromRGB(0, 255, 0)
- [x] Set Configuration.NameESPOutlineColour to Color3.fromRGB(0, 100, 0)

## 2. Replace Player Locking with NPC/Character Locking via workspace.Units
- [ ] Change target selection loop in AimbotLoop to iterate over workspace.Units:GetChildren(), excluding Player.Character
- [ ] Update TrackingHandler:InitializePlayers to handle workspace.Units instead of Players:GetPlayers()
- [ ] Add connections for workspace.Units.ChildAdded and ChildRemoved

## 3. Update Team Checking to Use TEAM.Value
- [ ] Modify IsReady function to check Target.TEAM.Value and Player.Character.TEAM.Value for team comparison
- [ ] Handle cases where TEAM.Value may not exist or Player.Character lacks it
- [ ] Apply team check only if Configuration.TeamCheck is enabled

## 4. Modify IsReady Function for NPCs
- [ ] Adjust IsReady to handle models without _Player (NPCs)
- [ ] Apply player-specific checks (FriendCheck, FollowCheck, VerifiedBadgeCheck, etc.) only if _Player exists
- [ ] Ensure checks for AliveCheck, GodCheck, WallCheck, etc., work for NPCs

## 5. Update ESP and Tracking for NPCs
- [ ] Modify ESPLibrary:Initialize to handle NPCs by setting self.Player to a mock table with Name "NPC" and TeamColor green
- [ ] Update NameESP.Text to handle NPCs appropriately
- [ ] Ensure ESP visuals work for models in workspace.Units

## 6. Final Testing and Cleanup
- [ ] Verify all changes are consistent
