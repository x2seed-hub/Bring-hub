local a = game:GetService("Players").LocalPlayer
local b = game:GetService("VirtualUser")
function totarget(c)
    local d = (c.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
    local e = game:service "TweenService"
    local f =
        TweenInfo.new(
        (game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart.Position - c.Position).Magnitude / 350,
        Enum.EasingStyle.Linear
    )
    if d < 50 then
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = c
    end
    local tween, g =
        pcall(
        function()
            tween = e:Create(game.Players.LocalPlayer.Character["HumanoidRootPart"], f, {CFrame = c})
            tween:Play()
        end
    )
end
local h = game.PlaceId
if h == 2753915549 then
    OldWorld = true
elseif h == 4442272183 then
    NewWorld = true
elseif h == 7449423635 then
    ThreeWorld = true
end
function AutoQuest()
    if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
        CheckQuest()
        repeat
            wait()
            totarget(CFrameQuest)
        until (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - CFrameQuest.Position).Magnitude <= 4
        wait(.1)
        local i = {[1] = "StartQuest", [2] = NaemQuest, [3] = LevelQuest}
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
    end
end
function CheckQuest()
    local j = game.Players.LocalPlayer.Data.Level.Value
    if OldWorld then
        if j == 1 or j <= 9 then
            Ms = "Bandit [Lv. 5]"
            NaemQuest = "BanditQuest1"
            LevelQuest = 1
            NameMon = "Bandit"
            CFrameQuest = CFrame.new(1061.66699, 16.5166187, 1544.52905)
            PosQuest = Vector3.new(1061.66699, 16.5166187, 1544.52905)
            CFrameMon = CFrame.new(1196.172, 11.8689699, 1616.95923)
            PosMon = Vector3.new(1199.31287, 52.2717781, 1536.91516)
        elseif j == 10 or j <= 14 then
            Ms = "Monkey [Lv. 14]"
            NaemQuest = "JungleQuest"
            LevelQuest = 1
            NameMon = "Monkey"
            CFrameQuest = CFrame.new(-1604.12012, 36.8521118, 154.23732)
            PosQuest = Vector3.new(-1604.12012, 36.8521118, 154.23732)
            CFrameMon = CFrame.new(-1619.10632, 21.7005882, 142.148117)
            PosMon = Vector3.new(-1772.4093017578, 60.860641479492, 54.872589111328)
        elseif j == 15 or j <= 29 then
            Ms = "Gorilla [Lv. 20]"
            NaemQuest = "JungleQuest"
            LevelQuest = 2
            NameMon = "Gorilla"
            CFrameQuest = CFrame.new(-1604.12012, 36.8521118, 154.23732)
            PosQuest = Vector3.new(-1604.12012, 36.8521118, 154.23732)
            CFrameMon = CFrame.new(-1129.8836669921875, 40.46354675292969, -525.4237060546875)
            PosMon = Vector3.new(-1223.52808, 6.27936459, -502.292664)
        elseif j == 30 or j <= 39 then
            Ms = "Pirate [Lv. 35]"
            NaemQuest = "BuggyQuest1"
            LevelQuest = 1
            NameMon = "Pirate"
            CFrameQuest = CFrame.new(-1139.59717, 4.75205183, 3825.16211)
            PosQuest = Vector3.new(-1139.59717, 4.75205183, 3825.16211)
            CFrameMon = CFrame.new(-1103.513427734375, 13.752052307128906, 3896.091064453125)
            PosMon = Vector3.new(-1219.32324, 4.75205183, 3915.63452)
        elseif j == 40 or j <= 59 then
            Ms = "Brute [Lv. 45]"
            NaemQuest = "BuggyQuest1"
            LevelQuest = 2
            NameMon = "Brute"
            CFrameQuest = CFrame.new(-1139.59717, 4.75205183, 3825.1621)
            PosQuest = Vector3.new(-1139.59717, 4.75205183, 3825.1621)
            CFrameMon = CFrame.new(-1140.083740234375, 14.809885025024414, 4322.92138671875)
            PosMon = Vector3.new(-1146.49646, 96.0936813, 4312.1333)
        elseif j == 60 or j <= 74 then
            Ms = "Desert Bandit [Lv. 60]"
            NaemQuest = "DesertQuest"
            LevelQuest = 1
            NameMon = "Desert Bandit"
            CFrameQuest = CFrame.new(897.031128, 6.43846416, 4388.9716)
            PosQuest = Vector3.new(897.031128, 6.43846416, 4388.9716)
            CFrameMon = CFrame.new(924.7998046875, 6.44867467880249, 4481.5859375)
            PosMon = Vector3.new(932.788818, 6.4503746, 4488.24609)
        elseif j == 75 or j <= 89 then
            Ms = "Desert Officer [Lv. 70]"
            NaemQuest = "DesertQuest"
            LevelQuest = 2
            NameMon = "Desert Officer"
            CFrameQuest = CFrame.new(897.031128, 6.43846416, 4388.9716)
            PosQuest = Vector3.new(897.031128, 6.43846416, 4388.9716)
            CFrameMon = CFrame.new(1608.2822265625, 8.614224433898926, 4371.00732421875)
            PosMon = Vector3.new(1580.03198, 4.61375761, 4366.86426)
        elseif j == 90 or j <= 99 then
            Ms = "Snow Bandit [Lv. 90]"
            NaemQuest = "SnowQuest"
            LevelQuest = 1
            NameMon = "Snow Bandits"
            CFrameQuest = CFrame.new(1384.14001, 87.272789, -1297.06482)
            PosQuest = Vector3.new(1384.14001, 87.272789, -1297.06482)
            CFrameMon = CFrame.new(1354.347900390625, 87.27277374267578, -1393.946533203125)
            PosMon = Vector3.new(1370.24316, 102.403511, -1411.52905)
        elseif j == 100 or j <= 119 then
            Ms = "Snowman [Lv. 100]"
            NaemQuest = "SnowQuest"
            LevelQuest = 2
            NameMon = "Snowman"
            CFrameQuest = CFrame.new(1384.14001, 87.272789, -1297.06482)
            PosQuest = Vector3.new(1384.14001, 87.272789, -1297.06482)
            CFrameMon = CFrame.new(1201.6412353515625, 144.57958984375, -1550.0670166015625)
            PosMon = Vector3.new(1370.24316, 102.403511, -1411.52905)
        elseif j == 120 or j <= 149 then
            Ms = "Chief Petty Officer [Lv. 120]"
            NaemQuest = "MarineQuest2"
            LevelQuest = 1
            NameMon = "Chief Petty Officer"
            CFrameQuest = CFrame.new(-5035.0835, 28.6520386, 4325.29443)
            PosQuest = Vector3.new(-5035.0835, 28.6520386, 4325.29443)
            CFrameMon = CFrame.new(-4931.1552734375, 65.793113708496, 4121.8393554688)
            PosMon = Vector3.new(-4882.8623, 22.6520386, 4255.53516)
        elseif j == 150 or j <= 174 then
            Ms = "Sky Bandit [Lv. 150]"
            NaemQuest = "SkyQuest"
            LevelQuest = 1
            NameMon = "Sky Bandit"
            CFrameQuest = CFrame.new(-4841.83447, 717.669617, -2623.96436)
            PosQuest = Vector3.new(-4841.83447, 717.669617, -2623.96436)
            CFrameMon = CFrame.new(-4953.20703125, 295.74420166015625, -2899.22900390625)
            PosMon = Vector3.new(-4970.74219, 294.544342, -2890.11353)
        elseif j == 175 or j <= 224 then
            Ms = "Dark Master [Lv. 175]"
            NaemQuest = "SkyQuest"
            LevelQuest = 2
            NameMon = "Dark Master"
            CFrameQuest = CFrame.new(-4841.83447, 717.669617, -2623.96436)
            PosQuest = Vector3.new(-4841.83447, 717.669617, -2623.96436)
            CFrameMon = CFrame.new(-5259.8447265625, 391.3976745605469, -2229.035400390625)
            PosMon = Vector3.new(-5220.58594, 430.693298, -2278.17456)
        elseif j == 225 or j <= 274 then
            Ms = "Toga Warrior [Lv. 225]"
            NaemQuest = "ColosseumQuest"
            LevelQuest = 1
            NameMon = "Toga Warrior"
            CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762)
            PosQuest = Vector3.new(-1576.11743, 7.38933945, -2983.30762)
            CFrameMon = CFrame.new(-1779.97583, 44.6077499, -2736.35474)
            PosMon = Vector3.new(-1779.97583, 44.6077499, -2736.35474)
        elseif j == 275 or j <= 299 then
            Ms = "Gladiator [Lv. 275]"
            NaemQuest = "ColosseumQuest"
            LevelQuest = 2
            NameMon = "Gladiato"
            CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762)
            PosQuest = Vector3.new(-1576.11743, 7.38933945, -2983.30762)
            CFrameMon = CFrame.new(-1274.75903, 58.1895943, -3188.16309)
            PosMon = Vector3.new(-1274.75903, 58.1895943, -3188.16309)
        elseif j == 300 or j <= 329 then
            Ms = "Military Soldier [Lv. 300]"
            NaemQuest = "MagmaQuest"
            LevelQuest = 1
            NameMon = "Military Soldier"
            CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998)
            PosQuest = Vector3.new(-5316.55859, 12.2370615, 8517.2998)
            CFrameMon = CFrame.new(-5363.01123, 41.5056877, 8548.47266)
            PosMon = Vector3.new(-5363.01123, 41.5056877, 8548.47266)
        elseif j == 300 or j <= 374 then
            Ms = "Military Spy [Lv. 330]"
            NaemQuest = "MagmaQuest"
            LevelQuest = 2
            NameMon = "Military Spy"
            CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998)
            PosQuest = Vector3.new(-5316.55859, 12.2370615, 8517.2998)
            CFrameMon = CFrame.new(-5787.99023, 120.864456, 8762.25293)
            PosMon = Vector3.new(-5787.99023, 120.864456, 8762.25293)
        elseif j == 375 or j <= 399 then
            Ms = "Fishman Warrior [Lv. 375]"
            NaemQuest = "FishmanQuest"
            LevelQuest = 1
            NameMon = "Fishman Warrior"
            CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504)
            PosQuest = Vector3.new(61122.5625, 18.4716396, 1568.16504)
            CFrameMon = CFrame.new(61163.8515625, 5.3073043823242, 1819.7841796875)
            PosMon = Vector3.new(61163.8515625, 5.3073043823242, 1819.7841796875)
        elseif j == 400 or j <= 449 then
            Ms = "Fishman Commando [Lv. 400]"
            NaemQuest = "FishmanQuest"
            LevelQuest = 2
            NameMon = "Fishman Commando"
            CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504)
            PosQuest = Vector3.new(61122.5625, 18.4716396, 1568.16504)
            CFrameMon = CFrame.new(61163.8515625, 5.3073043823242, 1819.7841796875)
            PosMon = Vector3.new(61163.8515625, 5.3073043823242, 1819.7841796875)
        elseif j == 450 or j <= 474 then
            Ms = "God's Guard [Lv. 450]"
            NaemQuest = "SkyExp1Quest"
            LevelQuest = 1
            NameMon = "God's Guards"
            CFrameQuest = CFrame.new(-4721.71436, 845.277161, -1954.20105)
            PosQuest = Vector3.new(-4721.71436, 845.277161, -1954.20105)
            CFrameMon = CFrame.new(-4716.95703, 853.089722, -1933.925427)
            PosMon = Vector3.new(-4716.95703, 853.089722, -1933.925427)
        elseif j == 475 or j <= 524 then
            Ms = "Shanda [Lv. 475]"
            NaemQuest = "SkyExp1Quest"
            LevelQuest = 2
            NameMon = "Shandas"
            CFrameQuest = CFrame.new(-7863.63672, 5545.49316, -379.826324)
            PosQuest = Vector3.new(-7863.63672, 5545.49316, -379.826324)
            CFrameMon = CFrame.new(-7685.12354, 5601.05127, -443.171509)
            PosMon = Vector3.new(-7685.12354, 5601.05127, -443.171509)
        elseif j == 525 or j <= 549 then
            Ms = "Royal Squad [Lv. 525]"
            NaemQuest = "SkyExp2Quest"
            LevelQuest = 1
            NameMon = "Royal Squad"
            CFrameQuest = CFrame.new(-7902.66895, 5635.96387, -1411.71802)
            PosQuest = Vector3.new(-7902.66895, 5635.96387, -1411.71802)
            CFrameMon = CFrame.new(-7685.02051, 5606.87842, -1442.729)
            PosMon = Vector3.new(-7685.02051, 5606.87842, -1442.729)
        elseif j == 550 or j <= 624 then
            Ms = "Royal Soldier [Lv. 550]"
            NaemQuest = "SkyExp2Quest"
            LevelQuest = 2
            NameMon = "Royal Soldier"
            CFrameQuest = CFrame.new(-7902.66895, 5635.96387, -1411.71802)
            PosQuest = Vector3.new(-7902.66895, 5635.96387, -1411.71802)
            CFrameMon = CFrame.new(-7864.44775, 5661.94092, -1708.22351)
            PosMon = Vector3.new(-7864.44775, 5661.94092, -1708.22351)
        elseif j == 625 or j <= 649 then
            Ms = "Galley Pirate [Lv. 625]"
            NaemQuest = "FountainQuest"
            LevelQuest = 1
            NameMon = "Galley Pirate"
            CFrameQuest = CFrame.new(5254.60156, 38.5011406, 4049.69678)
            PosQuest = Vector3.new(5254.60156, 38.5011406, 4049.69678)
            CFrameMon = CFrame.new(5595.06982, 41.5013695, 3961.47095)
            PosMon = Vector3.new(5595.06982, 41.5013695, 3961.47095)
        elseif j >= 650 then
            Ms = "Galley Captain [Lv. 650]"
            NaemQuest = "FountainQuest"
            LevelQuest = 2
            NameMon = "Galley Captain"
            CFrameQuest = CFrame.new(5254.60156, 38.5011406, 4049.69678)
            PosQuest = Vector3.new(5254.60156, 38.5011406, 4049.69678)
            CFrameMon = CFrame.new(5658.5752, 38.5361786, 4928.93506)
            PosMon = Vector3.new(5658.5752, 38.5361786, 4928.93506)
        end
    end
    if NewWorld then
        if j == 700 or j <= 724 then
            Ms = "Raider [Lv. 700]"
            NaemQuest = "Area1Quest"
            LevelQuest = 1
            NameMon = "Raider"
            CFrameQuest = CFrame.new(-424.080078, 73.0055847, 1836.91589)
            PosQuest = Vector3.new(-424.080078, 73.0055847, 1836.91589)
            CFrameMon = CFrame.new(-737.026123, 39.1748352, 2392.57959)
            PosMon = Vector3.new(-737.026123, 39.1748352, 2392.57959)
        elseif j == 725 or j <= 774 then
            Ms = "Mercenary [Lv. 725]"
            NaemQuest = "Area1Quest"
            LevelQuest = 2
            NameMon = "Mercenary"
            CFrameQuest = CFrame.new(-424.080078, 73.0055847, 1836.91589)
            PosQuest = Vector3.new(-424.080078, 73.0055847, 1836.91589)
            CFrameMon = CFrame.new(-973.731995, 95.8733215, 1836.46936)
            PosMon = Vector3.new(-973.731995, 95.8733215, 1836.46936)
        elseif j == 775 or j <= 874 then
            Ms = "Swan Pirate [Lv. 775]"
            NaemQuest = "Area2Quest"
            LevelQuest = 1
            NameMon = "Swan Pirate"
            CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321)
            PosQuest = Vector3.new(632.698608, 73.1055908, 918.666321)
            CFrameMon = CFrame.new(970.369446, 142.653198, 1217.3667)
            PosMon = Vector3.new(970.369446, 142.653198, 1217.3667)
        elseif j == 875 or j <= 899 then
            Ms = "Marine Lieutenant [Lv. 875]"
            NaemQuest = "MarineQuest3"
            LevelQuest = 1
            NameMon = "Marine Lieutenant"
            CFrameQuest =
                CFrame.new(
                -2442.99805,
                73.0160828,
                -3219.61304,
                -0.877783895,
                -7.71497781e-08,
                -0.479056865,
                -6.27637746e-08,
                1,
                -4.60420289e-08,
                0.479056865,
                -1.03475353e-08,
                -0.877783895
            )
            PosQuest =
                Vector3.new(
                -2442.99805,
                73.0160828,
                -3219.61304,
                -0.877783895,
                -7.71497781e-08,
                -0.479056865,
                -6.27637746e-08,
                1,
                -4.60420289e-08,
                0.479056865,
                -1.03475353e-08,
                -0.877783895
            )
            CFrameMon =
                CFrame.new(
                -3065.75806,
                102.075668,
                -3171.45386,
                -0.549014449,
                -3.08626227e-08,
                -0.835812867,
                1.2026228e-08,
                1,
                -4.4824862e-08,
                0.835812867,
                -3.46611735e-08,
                -0.549014449
            )
            PosMon =
                Vector3.new(
                -3065.75806,
                102.075668,
                -3171.45386,
                -0.549014449,
                -3.08626227e-08,
                -0.835812867,
                1.2026228e-08,
                1,
                -4.4824862e-08,
                0.835812867,
                -3.46611735e-08,
                -0.549014449
            )
        elseif j == 900 or j <= 949 then
            Ms = "Marine Captain [Lv. 900]"
            NaemQuest = "MarineQuest3"
            LevelQuest = 2
            NameMon = "Marine Captain"
            CFrameQuest =
                CFrame.new(
                -2442.99805,
                73.0160828,
                -3219.61304,
                -0.877783895,
                -7.71497781e-08,
                -0.479056865,
                -6.27637746e-08,
                1,
                -4.60420289e-08,
                0.479056865,
                -1.03475353e-08,
                -0.877783895
            )
            PosQuest =
                Vector3.new(
                -2442.99805,
                73.0160828,
                -3219.61304,
                -0.877783895,
                -7.71497781e-08,
                -0.479056865,
                -6.27637746e-08,
                1,
                -4.60420289e-08,
                0.479056865,
                -1.03475353e-08,
                -0.877783895
            )
            CFrameMon =
                CFrame.new(
                -1850.47278,
                89.8190918,
                -3206.01025,
                0.307623535,
                2.29538806e-08,
                0.951508164,
                -7.97129189e-08,
                1,
                1.64758374e-09,
                -0.951508164,
                -7.63543326e-08,
                0.307623535
            )
            PosMon =
                Vector3.new(
                -1850.47278,
                89.8190918,
                -3206.01025,
                0.307623535,
                2.29538806e-08,
                0.951508164,
                -7.97129189e-08,
                1,
                1.64758374e-09,
                -0.951508164,
                -7.63543326e-08,
                0.307623535
            )
        elseif j == 950 or j <= 974 then
            Ms = "Zombie [Lv. 950]"
            NaemQuest = "ZombieQuest"
            LevelQuest = 1
            NameMon = "Zombie"
            CFrameQuest = CFrame.new(-5492.79395, 48.5151672, -793.710571)
            PosQuest = Vector3.new(-5492.79395, 48.5151672, -793.710571)
            CFrameMon = CFrame.new(-5634.83838, 126.067039, -697.665039)
            PosMon = Vector3.new(-5634.83838, 126.067039, -697.665039)
        elseif j == 975 or j <= 999 then
            Ms = "Vampire [Lv. 975]"
            NaemQuest = "ZombieQuest"
            LevelQuest = 2
            NameMon = "Vampire"
            CFrameQuest = CFrame.new(-5492.79395, 48.5151672, -793.710571)
            PosQuest = Vector3.new(-5492.79395, 48.5151672, -793.710571)
            CFrameMon = CFrame.new(-6030.32031, 6.4377408, -1313.5564)
            PosMon = Vector3.new(-6030.32031, 6.4377408, -1313.5564)
        elseif j == 1000 or j <= 1049 then
            Ms = "Snow Trooper [Lv. 1000]"
            NaemQuest = "SnowMountainQuest"
            LevelQuest = 1
            NameMon = "Snow Trooper"
            CFrameQuest = CFrame.new(604.964966, 401.457062, -5371.69287)
            PosQuest = Vector3.new(604.964966, 401.457062, -5371.69287)
            CFrameMon = CFrame.new(535.893433, 401.457062, -5329.6958)
            PosMon = Vector3.new(535.893433, 401.457062, -5329.6958)
        elseif j == 1050 or j <= 1099 then
            Ms = "Winter Warrior [Lv. 1050]"
            NaemQuest = "SnowMountainQuest"
            LevelQuest = 2
            NameMon = "Winter Warrior"
            CFrameQuest = CFrame.new(604.964966, 401.457062, -5371.69287)
            PosQuest = Vector3.new(604.964966, 401.457062, -5371.69287)
            CFrameMon = CFrame.new(1223.7417, 454.575226, -5170.02148)
            PosMon = Vector3.new(1223.7417, 454.575226, -5170.02148)
        elseif j == 1100 or j <= 1124 then
            Ms = "Lab Subordinate [Lv. 1100]"
            NaemQuest = "IceSideQuest"
            LevelQuest = 1
            NameMon = "Lab Subordinate"
            CFrameQuest = CFrame.new(-6060.10693, 15.9868021, -4904.7876)
            PosQuest = Vector3.new(-6060.10693, 15.9868021, -4904.7876)
            CFrameMon = CFrame.new(-5769.2041, 37.9288292, -4468.38721)
            PosMon = Vector3.new(-5769.2041, 37.9288292, -4468.38721)
        elseif j == 1125 or j <= 1174 then
            Ms = "Horned Warrior [Lv. 1125]"
            NaemQuest = "IceSideQuest"
            LevelQuest = 2
            NameMon = "Horned Warrior"
            CFrameQuest = CFrame.new(-6060.10693, 15.9868021, -4904.7876)
            PosQuest = Vector3.new(-6060.10693, 15.9868021, -4904.7876)
            CFrameMon = CFrame.new(-6400.85889, 24.7645149, -5818.63574)
            PosMon = Vector3.new(-6400.85889, 24.7645149, -5818.63574)
        elseif j == 1175 or j <= 1199 then
            Ms = "Magma Ninja [Lv. 1175]"
            NaemQuest = "FireSideQuest"
            LevelQuest = 1
            NameMon = "Magma Ninja"
            CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223)
            PosQuest = Vector3.new(-5431.09473, 15.9868021, -5296.53223)
            CFrameMon = CFrame.new(-5496.65576, 58.6890411, -5929.76855)
            PosMon = Vector3.new(-5496.65576, 58.6890411, -5929.76855)
        elseif j == 1200 or j <= 1349 then
            Ms = "Lava Pirate [Lv. 1200]"
            NaemQuest = "FireSideQuest"
            LevelQuest = 2
            NameMon = "Lava Pirate"
            CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223)
            PosQuest = Vector3.new(-5431.09473, 15.9868021, -5296.53223)
            CFrameMon = CFrame.new(-5169.71729, 34.1234779, -4669.73633)
            PosMon = Vector3.new(-5169.71729, 34.1234779, -4669.73633)
        elseif j == 1350 or j <= 1374 then
            Ms = "Arctic Warrior [Lv. 1350]"
            NaemQuest = "FrostQuest"
            LevelQuest = 1
            NameMon = "Arctic Warrior"
            CFrameQuest = CFrame.new(5669.43506, 28.2117786, -6482.60107)
            PosQuest = Vector3.new(5669.43506, 28.2117786, -6482.60107)
            CFrameMon = CFrame.new(5995.07471, 57.3188477, -6183.47314)
            PosMon = Vector3.new(5995.07471, 57.3188477, -6183.47314)
        elseif j == 1375 or j <= 1424 then
            Ms = "Snow Lurker [Lv. 1375]"
            NaemQuest = "FrostQuest"
            LevelQuest = 2
            NameMon = "Snow Lurker"
            CFrameQuest = CFrame.new(5669.43506, 28.2117786, -6482.60107)
            PosQuest = Vector3.new(5669.43506, 28.2117786, -6482.60107)
            CFrameMon = CFrame.new(5518.00684, 60.5559731, -6828.80518)
            PosMon = Vector3.new(5518.00684, 60.5559731, -6828.80518)
        elseif j == 1425 or j <= 1449 then
            Ms = "Sea Soldier [Lv. 1425]"
            NaemQuest = "ForgottenQuest"
            LevelQuest = 1
            NameMon = "Sea Soldier"
            CFrameQuest = CFrame.new(-3052.99097, 236.881363, -10148.1943)
            PosQuest = Vector3.new(-3052.99097, 236.881363, -10148.1943)
            CFrameMon = CFrame.new(-3030.3696289063, 191.13464355469, -9859.7958984375)
            PosMon = Vector3.new(-3030.3696289063, 191.13464355469, -9859.7958984375)
        elseif j >= 1450 then
            Ms = "Water Fighter [Lv. 1450]"
            NaemQuest = "ForgottenQuest"
            LevelQuest = 2
            NameMon = "Water Fighter"
            CFrameQuest = CFrame.new(-3052.99097, 236.881363, -10148.1943)
            PosQuest = Vector3.new(-3052.99097, 236.881363, -10148.1943)
            CFrameMon = CFrame.new(-3436.7727050781, 290.52191162109, -10503.438476563)
            PosMon = Vector3.new(-3436.7727050781, 290.52191162109, -10503.438476563)
        end
    end
    if ThreeWorld then
        if j >= 1500 and j <= 1524 then
            Ms = "Pirate Millionaire [Lv. 1500]"
            NaemQuest = "PiratePortQuest"
            LevelQuest = 1
            NameMon = "Pirate Millionaire"
            CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984)
            PosQuest = Vector3.new(-290.074677, 42.9034653, 5581.58984)
            CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
            PosMon = Vector3.new(81.164993286133, 43.755737304688, 5724.7021484375)
        elseif j >= 1525 and j <= 1574 then
            Ms = "Pistol Billionaire [Lv. 1525]"
            NaemQuest = "PiratePortQuest"
            LevelQuest = 2
            NameMon = "Pistol Billionaire"
            CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984)
            PosQuest = Vector3.new(-290.074677, 42.9034653, 5581.58984)
            CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
            PosMon = Vector3.new(81.164993286133, 43.755737304688, 5724.7021484375)
        elseif j >= 1575 and j <= 1599 then
            Ms = "Dragon Crew Warrior [Lv. 1575]"
            NaemQuest = "AmazonQuest"
            LevelQuest = 1
            NameMon = "Dragon Crew Warrior"
            CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563)
            PosQuest = Vector3.new(5832.83594, 51.6806107, -1101.51563)
            CFrameMon = CFrame.new(6241.9951171875, 51.522083282471, -1243.9771728516)
            PosMon = Vector3.new(6241.9951171875, 51.522083282471, -1243.9771728516)
        elseif j >= 1600 and j <= 1624 then
            Ms = "Dragon Crew Archer [Lv. 1600]"
            NaemQuest = "AmazonQuest"
            LevelQuest = 2
            NameMon = "Dragon Crew Archer"
            CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563)
            PosQuest = Vector3.new(5832.83594, 51.6806107, -1101.51563)
            CFrameMon = CFrame.new(6488.9155273438, 383.38375854492, -110.66246032715)
            PosMon = Vector3.new(6488.9155273438, 383.38375854492, -110.66246032715)
        elseif j >= 1625 and j <= 1649 then
            Ms = "Female Islander [Lv. 1625]"
            NaemQuest = "AmazonQuest2"
            LevelQuest = 1
            NameMon = "Female Islander"
            CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676)
            PosQuest = Vector3.new(5448.86133, 601.516174, 751.130676)
            CFrameMon = CFrame.new(5825.2241210938, 682.89245605469, 704.57958984375)
            PosMon = Vector3.new(5825.2241210938, 682.89245605469, 704.57958984375)
        elseif j >= 1650 and j <= 1699 then
            Ms = "Giant Islander [Lv. 1650]"
            NaemQuest = "AmazonQuest2"
            LevelQuest = 2
            NameMon = "Giant Islander"
            CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676)
            PosQuest = Vector3.new(5448.86133, 601.516174, 751.130676)
            CFrameMon = CFrame.new(4530.3540039063, 656.75695800781, -131.60952758789)
            PosMon = Vector3.new(4530.3540039063, 656.75695800781, -131.60952758789)
        elseif j >= 1700 and j <= 1724 then
            Ms = "Marine Commodore [Lv. 1700]"
            NaemQuest = "MarineTreeIsland"
            LevelQuest = 1
            NameMon = "Marine Commodore"
            CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498)
            PosQuest = Vector3.new(2180.54126, 27.8156815, -6741.5498)
            CFrameMon = CFrame.new(2490.0844726563, 190.4232635498, -7160.0502929688)
            PosMon = Vector3.new(2490.0844726563, 190.4232635498, -7160.0502929688)
        elseif j >= 1725 and j <= 1774 then
            Ms = "Marine Rear Admiral [Lv. 1725]"
            NaemQuest = "MarineTreeIsland"
            LevelQuest = 2
            NameMon = "Marine Rear Admiral"
            CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498)
            PosQuest = Vector3.new(2180.54126, 27.8156815, -6741.5498)
            CFrameMon = CFrame.new(3951.3903808594, 229.11549377441, -6912.81640625)
            PosMon = Vector3.new(3951.3903808594, 229.11549377441, -6912.81640625)
        elseif j >= 1775 and j <= 1799 then
            Ms = "Fishman Raider [Lv. 1775]"
            NaemQuest = "DeepForestIsland3"
            LevelQuest = 1
            NameMon = "Fishman Raider"
            CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652)
            PosQuest = Vector3.new(-10581.6563, 330.872955, -8761.18652)
            CFrameMon = CFrame.new(-10322.400390625, 390.94473266602, -8580.0908203125)
            PosMon = Vector3.new(-10322.400390625, 390.94473266602, -8580.0908203125)
        elseif j >= 1800 and j <= 1824 then
            Ms = "Fishman Captain [Lv. 1800]"
            NaemQuest = "DeepForestIsland3"
            LevelQuest = 2
            NameMon = "Fishman Captain"
            CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652)
            PosQuest = Vector3.new(-10581.6563, 330.872955, -8761.18652)
            CFrameMon = CFrame.new(-11194.541992188, 442.02795410156, -8608.806640625)
            PosMon = Vector3.new(-11194.541992188, 442.02795410156, -8608.806640625)
        elseif j >= 1825 and j <= 1849 then
            Ms = "Forest Pirate [Lv. 1825]"
            NaemQuest = "DeepForestIsland"
            LevelQuest = 1
            NameMon = "Forest Pirate"
            CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137)
            PosQuest = Vector3.new(-13234.04, 331.488495, -7625.40137)
            CFrameMon = CFrame.new(-13225.809570313, 428.19387817383, -7753.1245117188)
            PosMon = Vector3.new(-13225.809570313, 428.19387817383, -7753.1245117188)
        elseif j >= 1850 and j <= 1899 then
            Ms = "Mythological Pirate [Lv. 1850]"
            NaemQuest = "DeepForestIsland"
            LevelQuest = 2
            NameMon = "Mythological Pirate"
            CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137)
            PosQuest = Vector3.new(-13234.04, 331.488495, -7625.40137)
            CFrameMon = CFrame.new(-13869.172851563, 564.95251464844, -7084.4135742188)
            PosMon = Vector3.new(-13869.172851563, 564.95251464844, -7084.4135742188)
        elseif j >= 1900 and j <= 1924 then
            Ms = "Jungle Pirate [Lv. 1900]"
            NaemQuest = "DeepForestIsland2"
            LevelQuest = 1
            NameMon = "Jungle Pirate"
            CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953)
            PosQuest = Vector3.new(-12680.3818, 389.971039, -9902.01953)
            CFrameMon = CFrame.new(-11982.221679688, 376.32522583008, -10451.415039063)
            PosMon = Vector3.new(-11982.221679688, 376.32522583008, -10451.415039063)
        elseif j >= 1925 and j <= 1974 then
            Ms = "Musketeer Pirate [Lv. 1925]"
            NaemQuest = "DeepForestIsland2"
            LevelQuest = 2
            NameMon = "Musketeer Pirate"
            CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953)
            PosQuest = Vector3.new(-12680.3818, 389.971039, -9902.01953)
            CFrameMon = CFrame.new(-13282.3046875, 496.23684692383, -9565.150390625)
            PosMon = Vector3.new(-13282.3046875, 496.23684692383, -9565.150390625)
        elseif j >= 1975 and j <= 1999 then
            Ms = "Reborn Skeleton [Lv. 1975]"
            NaemQuest = "HauntedQuest1"
            LevelQuest = 1
            NameMon = "Reborn Skeleton"
            CFrameQuest = CFrame.new(-9480.8271484375, 142.13066101074, 5566.0712890625)
            PosQuest = Vector3.new(-9480.8271484375, 142.13066101074, 5566.0712890625)
            CFrameMon = CFrame.new(-8817.880859375, 191.16761779785, 6298.6557617188)
            PosMon = Vector3.new(-8817.880859375, 191.16761779785, 6298.6557617188)
        elseif j >= 2000 and j <= 2024 then
            Ms = "Living Zombie [Lv. 2000]"
            NaemQuest = "HauntedQuest1"
            LevelQuest = 2
            NameMon = "Living Zombie"
            CFrameQuest = CFrame.new(-9480.8271484375, 142.13066101074, 5566.0712890625)
            PosQuest = Vector3.new(-9480.8271484375, 142.13066101074, 5566.0712890625)
            CFrameMon = CFrame.new(-10125.234375, 183.94705200195, 6242.013671875)
            PosMon = Vector3.new(-10125.234375, 183.94705200195, 6242.013671875)
        elseif j >= 2025 and j <= 2049 then
            Ms = "Demonic Soul [Lv. 2025]"
            NaemQuest = "HauntedQuest2"
            LevelQuest = 1
            NameMon = "Demonic Soul"
            CFrameQuest = CFrame.new(-9516.9931640625, 178.00651550293, 6078.4653320313)
            PosQuest = Vector3.new(-9516.9931640625, 178.00651550293, 6078.4653320313)
            CFrameMon = CFrame.new(-9712.03125, 204.69589233398, 6193.322265625)
            PosMon = Vector3.new(-9712.03125, 204.69589233398, 6193.322265625)
        elseif j >= 2050 and j <= 2100 then
            Ms = "Posessed Mummy [Lv. 2050]"
            NaemQuest = "HauntedQuest2"
            LevelQuest = 2
            NameMon = "Posessed Mummy"
            CFrameQuest = CFrame.new(-9516.9931640625, 178.00651550293, 6078.4653320313)
            PosQuest = Vector3.new(-9516.9931640625, 178.00651550293, 6078.4653320313)
            CFrameMon = CFrame.new(-9545.7763671875, 69.619895935059, 6339.5615234375)
            PosMon = Vector3.new(-9545.7763671875, 69.619895935059, 6339.5615234375)
        elseif j >= 2075 and j <= 2100 then
            Ms = "Peanut Scout [Lv. 2075]"
            NaemQuest = "NutsIslandQuest"
            LevelQuest = 1
            NameMon = "Peanut Scout"
            CFrameQuest =
                CFrame.new(
                -2104.17163,
                38.1299706,
                -10194.418,
                0.758814394,
                -1.38604395e-09,
                0.651306927,
                2.85280208e-08,
                1,
                -3.1108879e-08,
                -0.651306927,
                4.21863646e-08,
                0.758814394
            )
            PosQuest =
                Vector3.new(
                -2104.17163,
                38.1299706,
                -10194.418,
                0.758814394,
                -1.38604395e-09,
                0.651306927,
                2.85280208e-08,
                1,
                -3.1108879e-08,
                -0.651306927,
                4.21863646e-08,
                0.758814394
            )
            CFrameMon =
                CFrame.new(
                -2098.07544,
                192.611862,
                -10248.8867,
                0.983392298,
                -9.57031787e-08,
                0.181492642,
                8.7276355e-08,
                1,
                5.44169616e-08,
                -0.181492642,
                -3.76732068e-08,
                0.983392298
            )
            PosMon =
                Vector3.new(
                -2098.07544,
                192.611862,
                -10248.8867,
                0.983392298,
                -9.57031787e-08,
                0.181492642,
                8.7276355e-08,
                1,
                5.44169616e-08,
                -0.181492642,
                -3.76732068e-08,
                0.983392298
            )
        elseif j >= 2100 and j <= 2125 then
            Ms = "Peanut President [Lv. 2100]"
            NaemQuest = "NutsIslandQuest"
            LevelQuest = 2
            NameMon = "Peanut President"
            CFrameQuest =
                CFrame.new(
                -2104.17163,
                38.1299706,
                -10194.418,
                0.758814394,
                -1.38604395e-09,
                0.651306927,
                2.85280208e-08,
                1,
                -3.1108879e-08,
                -0.651306927,
                4.21863646e-08,
                0.758814394
            )
            PosQuest =
                Vector3.new(
                -2104.17163,
                38.1299706,
                -10194.418,
                0.758814394,
                -1.38604395e-09,
                0.651306927,
                2.85280208e-08,
                1,
                -3.1108879e-08,
                -0.651306927,
                4.21863646e-08,
                0.758814394
            )
            CFrameMon =
                CFrame.new(
                -1876.95959,
                192.610947,
                -10542.2939,
                0.0553516336,
                -2.83836812e-08,
                0.998466909,
                -6.89634405e-10,
                1,
                2.84654931e-08,
                -0.998466909,
                -2.26418861e-09,
                0.0553516336
            )
            PosMon =
                Vector3.new(
                -1876.95959,
                192.610947,
                -10542.2939,
                0.0553516336,
                -2.83836812e-08,
                0.998466909,
                -6.89634405e-10,
                1,
                2.84654931e-08,
                -0.998466909,
                -2.26418861e-09,
                0.0553516336
            )
        elseif j >= 2125 and j <= 2150 then
            Ms = "Ice Cream Chef [Lv. 2125]"
            NaemQuest = "IceCreamIslandQuest"
            LevelQuest = 1
            NameMon = "Ice Cream Chef"
            CFrameQuest =
                CFrame.new(
                -820.404358,
                65.8453293,
                -10965.5654,
                0.822534859,
                5.24448502e-08,
                -0.568714678,
                -2.08336317e-08,
                1,
                6.20846663e-08,
                0.568714678,
                -3.92184099e-08,
                0.822534859
            )
            PosQuest =
                Vector3.new(
                -820.404358,
                65.8453293,
                -10965.5654,
                0.822534859,
                5.24448502e-08,
                -0.568714678,
                -2.08336317e-08,
                1,
                6.20846663e-08,
                0.568714678,
                -3.92184099e-08,
                0.822534859
            )
            CFrameMon =
                CFrame.new(
                -821.614075,
                208.39537,
                -10990.7617,
                -0.870096624,
                3.18909272e-08,
                0.492881238,
                -1.8357893e-08,
                1,
                -9.71107568e-08,
                -0.492881238,
                -9.35439957e-08,
                -0.870096624
            )
            PosMon =
                Vector3.new(
                -821.614075,
                208.39537,
                -10990.7617,
                -0.870096624,
                3.18909272e-08,
                0.492881238,
                -1.8357893e-08,
                1,
                -9.71107568e-08,
                -0.492881238,
                -9.35439957e-08,
                -0.870096624
            )
        elseif j >= 2150 and j <= 2200 then
            Ms = "Ice Cream Commander [Lv. 2150]"
            NaemQuest = "IceCreamIslandQuest"
            LevelQuest = 2
            NameMon = "Ice Cream Commander"
            CFrameQuest =
                CFrame.new(
                -820.404358,
                65.8453293,
                -10965.5654,
                0.822534859,
                5.24448502e-08,
                -0.568714678,
                -2.08336317e-08,
                1,
                6.20846663e-08,
                0.568714678,
                -3.92184099e-08,
                0.822534859
            )
            PosQuest =
                Vector3.new(
                -820.404358,
                65.8453293,
                -10965.5654,
                0.822534859,
                5.24448502e-08,
                -0.568714678,
                -2.08336317e-08,
                1,
                6.20846663e-08,
                0.568714678,
                -3.92184099e-08,
                0.822534859
            )
            CFrameMon =
                CFrame.new(
                -821.614075,
                208.39537,
                -10990.7617,
                -0.870096624,
                3.18909272e-08,
                0.492881238,
                -1.8357893e-08,
                1,
                -9.71107568e-08,
                -0.492881238,
                -9.35439957e-08,
                -0.870096624
            )
            PosMon =
                Vector3.new(
                -821.614075,
                208.39537,
                -10990.7617,
                -0.870096624,
                3.18909272e-08,
                0.492881238,
                -1.8357893e-08,
                1,
                -9.71107568e-08,
                -0.492881238,
                -9.35439957e-08,
                -0.870096624
            )
        elseif j >= 2200 and j <= 2225 then
            Ms = "Cookie Crafter [Lv. 2200]"
            NaemQuest = "CakeQuest1"
            LevelQuest = 1
            NameMon = "Cookie Crafter"
            CFrameQuest = CFrame.new(-2021.29150390625, 37.79822540283203, -12027.0205078125)
            PosQuest = CFrame.new(-2021.29150390625, 37.79822540283203, -12027.0205078125)
            CFrameMon = CFrame.new(-2272.864013671875, 146.5398406982422, -12189.0478515625)
            PosMon = CFrame.new(-2272.864013671875, 146.5398406982422, -12189.0478515625)
        elseif j >= 2225 and j <= 2250 then
            Ms = "Cake Guard [Lv. 2225]"
            NaemQuest = "CakeQuest1"
            LevelQuest = 2
            NameMon = "Cake Guard"
            CFrameQuest = CFrame.new(-2021.29150390625, 37.79822540283203, -12027.0205078125)
            PosQuest = CFrame.new(-2021.29150390625, 37.79822540283203, -12027.0205078125)
            CFrameMon = CFrame.new(-1823.2464599609375, 210.2261505126953, -12292.82421875)
            PosMon = CFrame.new(-1823.2464599609375, 210.2261505126953, -12292.82421875)
        elseif j >= 2250 and j <= 2275 then
            Ms = "Baking Staff [Lv. 2250]"
            NaemQuest = "CakeQuest2"
            LevelQuest = 1
            NameMon = "Baking Staff"
            CFrameQuest = CFrame.new(-1928.324462890625, 37.798133850097656, -12843.0517578125)
            PosQuest = CFrame.new(-1928.324462890625, 37.798133850097656, -12843.0517578125)
            CFrameMon = CFrame.new(-2000.436767578125, 385.1067810058594, -13096.3330078125)
            PosMon = CFrame.new(-2000.436767578125, 385.1067810058594, -13096.3330078125)
        elseif j >= 2275 then
            Ms = "Head Baker [Lv. 2275]"
            NaemQuest = "CakeQuest2"
            LevelQuest = 2
            NameMon = "Head Baker"
            CFrameQuest = CFrame.new(-1928.324462890625, 37.798133850097656, -12843.0517578125)
            PosQuest = CFrame.new(-1928.324462890625, 37.798133850097656, -12843.0517578125)
            CFrameMon = CFrame.new(-2161.431640625, 93.0169448852539, -12989.7822265625)
            PosMon = CFrame.new(-2161.431640625, 93.0169448852539, -12989.7822265625)
        end
    end
end
function TP()
    CheckQuest()
    local k = game:GetService("Workspace").Enemies:GetChildren()
    local j = game.Players.LocalPlayer.Data.Level.Value
    if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
        for l, m in pairs(k) do
            if m.Name == Ms then
                if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
                end
                game.Players.LocalPlayer.Character.HumanoidRootPart.Size = Vector3.new(2, 2.02, 1)
                m.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
                EquipWeapon(getgenv().SelectWeapon)
                totarget(m.HumanoidRootPart.CFrame * CFrame.new(24, 0, 0))
                game:GetService "VirtualUser":CaptureController()
                game:GetService "VirtualUser":Button1Down(Vector2.new(1280, 672))
            end
        end
    end
end
function EquipWeapon(n)
    if game.Players.LocalPlayer.Backpack:FindFirstChild(n) then
        local o = game.Players.LocalPlayer.Backpack:FindFirstChild(n)
        wait()
        game.Players.LocalPlayer.Character.Humanoid:EquipTool(o)
    end
end
if game:GetService("CoreGui"):FindFirstChild("Nigga") then
    game:GetService("CoreGui"):FindFirstChild("Nigga"):Destroy()
end
local p = Instance.new("ScreenGui")
local q = Instance.new("TextButton")
local r = Instance.new("UICorner")
p.Name = "Open/Close"
p.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
p.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
q.Name = "Open/Close2"
q.Parent = p
q.BackgroundColor3 = Color3.fromRGB(85, 255, 127)
q.Position = UDim2.new(0.141116098, 0, 0.16842106, 0)
q.Size = UDim2.new(0, 64, 0, 50)
q.Font = Enum.Font.GothamBold
q.Text = "OPEN"
q.TextColor3 = Color3.fromRGB(0, 0, 0)
q.TextSize = 14.000
q.MouseButton1Click:Connect(
    function()
        game:GetService("CoreGui"):FindFirstChild("Nigga").Enabled =
            not game:GetService("CoreGui"):FindFirstChild("Nigga").Enabled
    end
)
r.CornerRadius = UDim.new(0, 3)
r.Parent = q
local s = {}
local t = game:GetService("UserInputService")
local u = game:GetService("TweenService")
local v = game:GetService("RunService")
local a = game:GetService("Players").LocalPlayer
local w = a:GetMouse()
local x = game:GetService("HttpService")
local y
local z
local A
local B = {}
y =
    B["pfp"] or
    "https://www.roblox.com/headshot-thumbnail/image?userId=" ..
        game.Players.LocalPlayer.UserId .. "&width=420&height=420&format=png"
z = B["user"] or game.Players.LocalPlayer.DisplayName
A = B["tag"] or tostring(math.random(0001, 9999))
local function C()
    B["pfp"] = y
    B["user"] = z
    B["tag"] = A
    writefile("", x:JSONEncode(B))
end
local function D(E, F)
    local G = nil
    local H = nil
    local I = nil
    local J = nil
    local function K(L)
        local M = L.Position - I
        local N = UDim2.new(J.X.Scale, J.X.Offset + M.X, J.Y.Scale, J.Y.Offset + M.Y)
        local O = u:Create(F, TweenInfo.new(0.15), {Position = N})
        O:Play()
    end
    E.InputBegan:Connect(
        function(L)
            if L.UserInputType == Enum.UserInputType.MouseButton1 or L.UserInputType == Enum.UserInputType.Touch then
                G = true
                I = L.Position
                J = F.Position
                L.Changed:Connect(
                    function()
                        if L.UserInputState == Enum.UserInputState.End then
                            G = false
                        end
                    end
                )
            end
        end
    )
    E.InputChanged:Connect(
        function(L)
            if L.UserInputType == Enum.UserInputType.MouseMovement or L.UserInputType == Enum.UserInputType.Touch then
                H = L
            end
        end
    )
    t.InputChanged:Connect(
        function(L)
            if L == H and G then
                K(L)
            end
        end
    )
end
local function P(F)
    spawn(
        function()
            local Q = Instance.new("ImageLabel")
            Q.Name = "Ripple"
            Q.Parent = F
            Q.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            Q.BackgroundTransparency = 1.000
            Q.ZIndex = 8
            Q.Image = "rbxassetid://2708891598"
            Q.ImageTransparency = 0.800
            Q.ScaleType = Enum.ScaleType.Fit
            Q.Position = UDim2.new(w.X / F.AbsoluteSize.Y, 0, w.Y / F.AbsoluteSize.X, 0)
            u:Create(
                Q,
                TweenInfo.new(1, Enum.EasingStyle.Back, Enum.EasingDirection.Out),
                {Position = UDim2.new(-5.5, 0, -5.5, 0), Size = UDim2.new(3, 0, 3, 0)}
            ):Play()
            wait(0.5)
            u:Create(Q, TweenInfo.new(1, Enum.EasingStyle.Back, Enum.EasingDirection.Out), {ImageTransparency = 1}):Play(

            )
            wait(1)
            Q:Destroy()
        end
    )
end
wait(1)
local R = Instance.new("ScreenGui")
R.Name = "Nigga"
R.Parent = game:GetService("CoreGui")
R.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
function s:Window(S, T, U)
    local V = T or Color3.fromRGB(112, 255, 188) or _G.Color
    local W = U or Enum.KeyCode.RightControl or _G.Toggle
    local X = ""
    local Y = false
    local Z = false
    local _ = false
    local a0 = Instance.new("Frame")
    local a1 = Instance.new("UIGradient")
    local a2 = Instance.new("Frame")
    local a3 = Instance.new("TextLabel")
    local a4 = Instance.new("ImageLabel")
    local a5 = Instance.new("TextButton")
    local a6 = Instance.new("ImageLabel")
    local a7 = Instance.new("Folder")
    local a8 = Instance.new("Frame")
    local a9 = Instance.new("UICorner")
    local aa = Instance.new("Frame")
    local ab = Instance.new("UICorner")
    local ac = Instance.new("ImageLabel")
    local ad = Instance.new("UICorner")
    local ae = Instance.new("ImageLabel")
    local af = Instance.new("TextLabel")
    local ag = Instance.new("TextLabel")
    local ah = Instance.new("Frame")
    local ai = Instance.new("ScrollingFrame")
    local aj = Instance.new("UIListLayout")
    local ak = Instance.new("UIPadding")
    local al = Instance.new("Frame")
    local am = Instance.new("Frame")
    local an = Instance.new("ImageLabel")
    local ao = Instance.new("UICorner")
    a0.Name = "MainFrame"
    a0.Parent = R
    a0.AnchorPoint = Vector2.new(0.5, 0.5)
    a0.BackgroundColor3 = Color3.fromRGB(32, 34, 37)
    a0.BackgroundTransparency = 1
    a0.BorderSizePixel = 0
    a0.ClipsDescendants = true
    a0.Position = UDim2.new(0.5, 0, 0.5, 0)
    a0.Size = UDim2.new(0, 618, 0, 407)
    local ap = false
    t.InputBegan:Connect(
        function(aq, ar)
            pcall(
                function()
                    if aq.KeyCode == W then
                        if ap == false then
                            a0:TweenSize(
                                UDim2.new(0, 0, 0, 0),
                                Enum.EasingDirection.Out,
                                Enum.EasingStyle.Quart,
                                .3,
                                true
                            )
                            wait(.3)
                            R.Enabled = false
                            ap = true
                        else
                            R.Enabled = true
                            a0:TweenSize(
                                UDim2.new(0, 618, 0, 407),
                                Enum.EasingDirection.Out,
                                Enum.EasingStyle.Quart,
                                .3,
                                true
                            )
                            ap = false
                        end
                    end
                end
            )
        end
    )
    am.Name = "GlowFrame"
    am.Parent = a0
    am.BackgroundTransparency = 1
    am.Position = UDim2.new(0, 0.5, 0, 17.5)
    am.Size = UDim2.new(0.625, 0, 0.763, 0)
    am.BackgroundColor3 = V
    ao.CornerRadius = UDim.new(0, 7)
    ao.Name = "GlowFrameCorner"
    ao.Parent = am
    an.Name = "Glow"
    an.Parent = am
    an.BackgroundColor3 = V
    an.BackgroundTransparency = 1
    an.BorderSizePixel = 0
    an.Size = UDim2.new(0.625, 0, 0.763, 0)
    an.ZIndex = 2
    an.Image = "rbxassetid://5028857084"
    an.ImageColor3 = V
    an.ScaleType = Enum.ScaleType.Slice
    a2.Name = "TopFrame"
    a2.Parent = a0
    a2.BackgroundColor3 = Color3.fromRGB(32, 34, 37)
    a2.BackgroundTransparency = 1.000
    a2.BorderSizePixel = 0
    a2.Position = UDim2.new(-0.000658480625, 0, 0, 0)
    a2.Size = UDim2.new(0, 681, 0, 65)
    al.Name = "TopFrameHolder"
    al.Parent = a2
    al.BackgroundColor3 = Color3.fromRGB(32, 34, 37)
    al.BackgroundTransparency = 1.000
    al.BorderSizePixel = 0
    al.Position = UDim2.new(-0.000658480625, 0, 0, 0)
    al.Size = UDim2.new(0, 681, 0, 22)
    a3.Name = "Title"
    a3.Parent = a2
    a3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    a3.BackgroundTransparency = 1.000
    a3.Position = UDim2.new(0.0102790017, 0, 0, 0)
    a3.Size = UDim2.new(0, 192, 0, 23)
    a3.Font = Enum.Font.Gotham
    a3.Text = S
    a3.TextColor3 = Color3.fromRGB(255, 255, 255)
    a3.TextSize = 13.000
    a3.TextXAlignment = Enum.TextXAlignment.Left
    a7.Name = "ServersHolder"
    a7.Parent = al
    a8.Name = "Userpad"
    a8.Parent = al
    a8.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    a8.BackgroundTransparency = 1
    a8.BorderSizePixel = 0
    a8.Position = UDim2.new(0.0010243297, 0, 15.8807148, 0)
    a8.Size = UDim2.new(0, 179, 0, 43)
    aa.Name = "UserIcon"
    aa.Parent = a8
    aa.BackgroundColor3 = Color3.fromRGB(29, 29, 29)
    aa.BackgroundTransparency = 1
    aa.BorderSizePixel = 0
    aa.Position = UDim2.new(0.0340000018, 0, 0.123999998, 0)
    aa.Size = UDim2.new(0, 32, 0, 32)
    ac.Name = "UserImage"
    ac.Parent = aa
    ac.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    ac.BackgroundTransparency = 1.000
    ac.Size = UDim2.new(0, 32, 0, 32)
    ac.Image = y
    ae.Name = "UserImage"
    ae.Parent = ac
    ae.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    ae.BackgroundTransparency = 1.000
    ae.ImageColor3 = Color3.fromRGB(23, 23, 23)
    ae.Size = UDim2.new(0, 32, 0, 32)
    ae.Image = "rbxassetid://4031889928"
    ae.ImageColor3 = Color3.fromRGB(27, 27, 27)
    af.Name = "UserName"
    af.Parent = a8
    af.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    af.BackgroundTransparency = 1.000
    af.BorderSizePixel = 0
    af.Position = UDim2.new(0.230000004, 0, 0.115999997, 0)
    af.Size = UDim2.new(0, 98, 0, 17)
    af.Font = Enum.Font.GothamSemibold
    af.TextColor3 = V
    af.TextSize = 13.000
    af.TextXAlignment = Enum.TextXAlignment.Left
    af.ClipsDescendants = true
    ag.Name = "UserTag"
    ag.Parent = a8
    ag.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    ag.BackgroundTransparency = 1.000
    ag.BorderSizePixel = 0
    ag.Position = UDim2.new(0.230000004, 0, 0.455000013, 0)
    ag.Size = UDim2.new(0, 95, 0, 17)
    ag.Font = Enum.Font.Gotham
    ag.TextColor3 = V
    ag.TextSize = 13.000
    ag.TextTransparency = 0.300
    ag.TextXAlignment = Enum.TextXAlignment.Left
    af.Text = z
    ag.Text = "N/A"
    spawn(
        function()
            while wait() do
                ag.Text = "PrimeHub"
            end
        end
    )
    ah.Name = "ServersHoldFrame"
    ah.Parent = a0
    ah.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    ah.BackgroundTransparency = 1.000
    ah.BorderColor3 = V
    ah.Size = UDim2.new(0, 71, 0, 396)
    ai.Name = "ServersHold"
    ai.Parent = ah
    ai.Active = true
    ai.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
    ai.BackgroundTransparency = 1.000
    ai.BorderSizePixel = 0
    ai.Position = UDim2.new(-0.000359333731, 0, 0.0580808073, 0)
    ai.Size = UDim2.new(0, 71, 0, 373)
    ai.ScrollBarThickness = 1
    ai.ScrollBarImageTransparency = 1
    ai.CanvasSize = UDim2.new(0, 0, 0, 0)
    aj.Name = "ServersHoldLayout"
    aj.Parent = ai
    aj.SortOrder = Enum.SortOrder.LayoutOrder
    aj.Padding = UDim.new(0, 7)
    ak.Name = "ServersHoldPadding"
    ak.Parent = ai
    function s:Notification(as, at, au)
        local av = Instance.new("Frame")
        local aw = Instance.new("UICorner")
        local ax = Instance.new("Frame")
        local ay = Instance.new("UICorner")
        local az = Instance.new("Frame")
        local aA = Instance.new("UICorner")
        local aB = Instance.new("Frame")
        local aC = Instance.new("TextLabel")
        local aD = Instance.new("TextLabel")
        local aE = Instance.new("TextButton")
        local aF = Instance.new("UICorner")
        av.Name = "NotificationHolderMain"
        av.Parent = a0
        av.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
        av.BackgroundTransparency = 1
        av.BorderSizePixel = 0
        av.Position = UDim2.new(0, -1, 0.0460000017, 0)
        av.Size = UDim2.new(0, 676, 0, 374)
        u:Create(av, TweenInfo.new(.2, Enum.EasingStyle.Back, Enum.EasingDirection.Out), {BackgroundTransparency = 0.1}):Play(

        )
        aw.CornerRadius = UDim.new(0, 7)
        aw.Name = "NotificationHolderMainCorner"
        aw.Parent = av
        ax.Name = "Notification"
        ax.Parent = av
        ax.AnchorPoint = Vector2.new(0.5, 0.5)
        ax.BackgroundColor3 = Color3.fromRGB(29, 29, 29)
        ax.ClipsDescendants = true
        ax.Position = UDim2.new(0.524819076, 0, 0.469270051, 0)
        ax.Size = UDim2.new(0, -43, 0, 0)
        ax.BackgroundTransparency = 1
        ax:TweenSize(UDim2.new(0, 346, 0, 176), Enum.EasingDirection.Out, Enum.EasingStyle.Back, .2, true)
        u:Create(ax, TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundTransparency = 0}):Play(

        )
        ay.CornerRadius = UDim.new(0, 5)
        ay.Name = "NotificationCorner"
        ay.Parent = ax
        az.Name = "UnderBar"
        az.Parent = ax
        az.BackgroundColor3 = Color3.fromRGB(10, 10, 10)
        az.Position = UDim2.new(-0.000297061284, 0, 0.945048928, 0)
        az.Size = UDim2.new(0, 346, 0, 10)
        aA.CornerRadius = UDim.new(0, 5)
        aA.Name = "UnderBarCorner"
        aA.Parent = az
        aB.Name = "UnderBarFrame"
        aB.Parent = az
        aB.BackgroundColor3 = Color3.fromRGB(14, 14, 14)
        aB.BorderSizePixel = 0
        aB.Position = UDim2.new(-0.000297061284, 0, -3.76068449, 0)
        aB.Size = UDim2.new(0, 346, 0, 40)
        aC.Name = "Text1"
        aC.Parent = ax
        aC.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        aC.BackgroundTransparency = 1.000
        aC.Position = UDim2.new(-0.000594122568, 0, 0.0202020202, 0)
        aC.Size = UDim2.new(0, 346, 0, 68)
        aC.Font = Enum.Font.GothamSemibold
        aC.Text = as
        aC.TextColor3 = V
        aC.TextSize = 20.000
        aD.Name = "Text2"
        aD.Parent = ax
        aD.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        aD.BackgroundTransparency = 1.000
        aD.Position = UDim2.new(0.106342293, 0, 0.317724228, 0)
        aD.Size = UDim2.new(0, 272, 0, 63)
        aD.Font = Enum.Font.Gotham
        aD.Text = at
        aD.TextColor3 = V
        aD.TextSize = 14.000
        aD.TextWrapped = true
        aE.Name = "AlrightBtn"
        aE.Parent = ax
        aE.BackgroundColor3 = V
        aE.Position = UDim2.new(0.0332369953, 0, 0.789141417, 0)
        aE.Size = UDim2.new(0, 322, 0, 27)
        aE.Font = Enum.Font.Gotham
        aE.Text = au
        aE.TextColor3 = Color3.fromRGB(23, 23, 23)
        aE.TextSize = 13.000
        aE.AutoButtonColor = false
        aF.CornerRadius = UDim.new(0, 4)
        aF.Name = "AlrightCorner"
        aF.Parent = aE
        aE.MouseButton1Click:Connect(
            function()
                u:Create(
                    av,
                    TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                ):Play()
                ax:TweenSize(UDim2.new(0, 0, 0, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .2, true)
                u:Create(
                    ax,
                    TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundTransparency = 1}
                ):Play()
                wait()
                av:Destroy()
            end
        )
        aE.MouseEnter:Connect(
            function()
                u:Create(
                    aE,
                    TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = Color3.fromRGB(23, 23, 23), TextColor3 = V}
                ):Play()
            end
        )
        aE.MouseLeave:Connect(
            function()
                u:Create(
                    aE,
                    TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                    {BackgroundColor3 = V, TextColor3 = Color3.fromRGB(23, 23, 23)}
                ):Play()
            end
        )
    end
    D(a2, a0)
    ak.PaddingLeft = UDim.new(0, 14)
    local aG = {}
    function aG:Server(S, aH)
        local aI = false
        local aJ = ""
        local aK = Instance.new("TextButton")
        local aL = Instance.new("UICorner")
        local aM = Instance.new("ImageLabel")
        local aN = Instance.new("Frame")
        local aO = Instance.new("UICorner")
        aK.Name = S .. "Server"
        aK.Parent = ai
        aK.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
        aK.Position = UDim2.new(0.125, 0, 0, 0)
        aK.Size = UDim2.new(0, 47, 0, 47)
        aK.AutoButtonColor = false
        aK.Font = Enum.Font.Gotham
        aK.Text = ""
        aK.BackgroundTransparency = 1
        aK.TextTransparency = 1
        aK.TextColor3 = Color3.fromRGB(233, 25, 42)
        aK.TextSize = 18.000
        aL.CornerRadius = UDim.new(1, 0)
        aL.Name = "ServerCorner"
        aL.Parent = aK
        aN.Name = "ServerWhiteFrame"
        aN.Parent = aK
        aN.AnchorPoint = Vector2.new(0.5, 0.5)
        aN.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        aN.BackgroundTransparency = 1
        aN.Position = UDim2.new(-0.347378343, 0, 0.502659559, 0)
        aN.Size = UDim2.new(0, 11, 0, 10)
        aO.CornerRadius = UDim.new(1, 0)
        aO.Name = "ServerWhiteFrameCorner"
        aO.Parent = aN
        ai.CanvasSize = UDim2.new(0, 0, 0, aj.AbsoluteContentSize.Y)
        local aP = Instance.new("Frame")
        local aQ = Instance.new("Frame")
        local aR = Instance.new("TextLabel")
        local am = Instance.new("Frame")
        local an = Instance.new("ImageLabel")
        local aS = Instance.new("Frame")
        local aT = Instance.new("UICorner")
        local aU = Instance.new("Frame")
        local aV = Instance.new("UICorner")
        local aW = Instance.new("TextLabel")
        local aX = Instance.new("TextLabel")
        local aY = Instance.new("Frame")
        local aZ = Instance.new("UICorner")
        local a_ = Instance.new("ImageLabel")
        local b0 = Instance.new("ScrollingFrame")
        local b1 = Instance.new("UIListLayout")
        local b2 = Instance.new("UIPadding")
        local b3 = Instance.new("TextLabel")
        local b4 = Instance.new("TextLabel")
        local b5 = Instance.new("ImageLabel")
        aP.Name = "ServerFrame"
        aP.Parent = a7
        aP.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
        aP.BorderSizePixel = 0
        aP.ClipsDescendants = true
        aP.Position = UDim2.new(0.005356875, 0, 0.32262593, 13)
        aP.Size = UDim2.new(0, 609, 0, 373)
        aP.Visible = false
        aQ.Name = "ServerTitleFrame"
        aQ.Parent = aP
        aQ.BackgroundColor3 = Color3.fromRGB(47, 49, 54)
        aQ.BackgroundTransparency = 1.000
        aQ.BorderSizePixel = 0
        aQ.Position = UDim2.new(-0.0010054264, 0, -0.000900391256, 0)
        aQ.Size = UDim2.new(0, 180, 0, 40)
        aR.Name = "ServerTitle"
        aR.Parent = aQ
        aR.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        aR.BackgroundTransparency = 1.000
        aR.BorderSizePixel = 0
        aR.Position = UDim2.new(0.0851359761, 0, 0, 0)
        aR.Size = UDim2.new(0, 97, 0, 39)
        aR.Font = Enum.Font.GothamSemibold
        aR.Text = S
        aR.TextColor3 = V
        aR.TextSize = 15.000
        aR.TextXAlignment = Enum.TextXAlignment.Left
        am.Name = "GlowFrame"
        am.Parent = aP
        am.BackgroundColor3 = Color3.fromRGB(47, 49, 54)
        am.BackgroundTransparency = 1.000
        am.BorderSizePixel = 0
        am.Position = UDim2.new(-0.0010054264, 0, -0.000900391256, 0)
        am.Size = UDim2.new(0, 609, 0, 40)
        an.Name = "Glow"
        an.Parent = am
        an.BackgroundColor3 = V
        an.BackgroundTransparency = 1.000
        an.BorderSizePixel = 0
        an.Position = UDim2.new(0, -15, 0, -15)
        an.Size = UDim2.new(1, 30, 1, 30)
        an.ZIndex = 0
        an.Image = "rbxassetid://4996891970"
        an.ImageColor3 = Color3.fromRGB(15, 15, 15)
        an.ScaleType = Enum.ScaleType.Slice
        an.SliceCenter = Rect.new(20, 20, 280, 280)
        aS.Name = "ServerContentFrame"
        aS.Parent = aP
        aS.BackgroundColor3 = Color3.fromRGB(47, 49, 54)
        aS.BackgroundTransparency = 1.000
        aS.BorderSizePixel = 0
        aS.Position = UDim2.new(-0.0010054264, 0, 0.106338218, 0)
        aS.Size = UDim2.new(0, 180, 0, 333)
        aT.CornerRadius = UDim.new(0, 7)
        aT.Name = "ServerCorner"
        aT.Parent = aP
        aU.Name = "ChannelTitleFrame"
        aU.Parent = aP
        aU.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
        aU.BorderSizePixel = 0
        aU.Position = UDim2.new(0.294561088, 0, -0.000900391256, 0)
        aU.Size = UDim2.new(0, 429, 0, 40)
        aV.CornerRadius = UDim.new(0, 7)
        aV.Name = "ChannelTitleFrameCorner"
        aV.Parent = aU
        b4.Name = "TimeGlobal"
        b4.Parent = aU
        b4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        b4.Position = UDim2.new(0.7062470865, 0, 0, 0)
        b4.Size = UDim2.new(0, 95, 0, 39)
        b4.BackgroundTransparency = 1
        b4.ZIndex = 3
        b4.Font = Enum.Font.GothamSemibold
        b4.TextColor3 = V
        b4.TextSize = 15.000
        b4.TextXAlignment = Enum.TextXAlignment.Left
        b4.Text = ""
        aX.Name = "ChannelTitle"
        aX.Parent = aU
        aX.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        aX.BackgroundTransparency = 1.000
        aX.BorderSizePixel = 0
        aX.Position = UDim2.new(0.0662470865, 0, 0, 0)
        aX.Size = UDim2.new(0, 95, 0, 39)
        aX.Font = Enum.Font.GothamSemibold
        aX.Text = ""
        aX.TextColor3 = V
        aX.TextSize = 15.000
        aX.TextXAlignment = Enum.TextXAlignment.Left
        aY.Name = "ChannelContentFrame"
        aY.Parent = aP
        aY.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
        aY.BorderSizePixel = 0
        aY.ClipsDescendants = true
        aY.Position = UDim2.new(0.294561088, 0, 0.106338218, 0)
        aY.Size = UDim2.new(0, 429, 0, 333)
        aZ.CornerRadius = UDim.new(0, 7)
        aZ.Name = "ChannelContentFrameCorner"
        aZ.Parent = aY
        a_.Name = "GlowChannel"
        a_.Parent = aY
        a_.BackgroundColor3 = V
        a_.BackgroundTransparency = 1.000
        a_.BorderSizePixel = 0
        a_.Position = UDim2.new(0, -33, 0, -91)
        a_.Size = UDim2.new(1.06396091, 30, 0.228228226, 30)
        a_.ZIndex = 0
        a_.Image = "rbxassetid://4996891970"
        a_.ImageColor3 = Color3.fromRGB(15, 15, 15)
        a_.ScaleType = Enum.ScaleType.Slice
        a_.SliceCenter = Rect.new(20, 20, 280, 280)
        b0.Name = "ServerChannelHolder"
        b0.Parent = aS
        b0.Active = true
        b0.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        b0.BackgroundTransparency = 1.000
        b0.BorderSizePixel = 0
        b0.Position = UDim2.new(0.00535549596, 0, 0.0241984241, 0)
        b0.Selectable = false
        b0.Size = UDim2.new(0, 179, 0, 278)
        b0.CanvasSize = UDim2.new(0, 0, 0, 0)
        b0.ScrollBarThickness = 4
        b0.ScrollBarImageColor3 = V
        b0.ScrollBarImageTransparency = 1
        b1.Name = "ServerChannelHolderLayout"
        b1.Parent = b0
        b1.SortOrder = Enum.SortOrder.LayoutOrder
        b1.Padding = UDim.new(0, 4)
        b2.Name = "ServerChannelHolderPadding"
        b2.Parent = b0
        b2.PaddingLeft = UDim.new(0, 9)
        b0.MouseEnter:Connect(
            function()
                b0.ScrollBarImageTransparency = 0
            end
        )
        b0.MouseLeave:Connect(
            function()
                b0.ScrollBarImageTransparency = 1
            end
        )
        aK.MouseEnter:Connect(
            function()
                if X ~= aK.Name then
                    u:Create(
                        aK,
                        TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                        {BackgroundColor3 = Color3.fromRGB(23, 23, 23)}
                    ):Play()
                    u:Create(
                        aL,
                        TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                        {CornerRadius = UDim.new(0, 15)}
                    ):Play()
                    aN:TweenSize(UDim2.new(0, 11, 0, 27), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                end
            end
        )
        aK.MouseLeave:Connect(
            function()
                if X ~= aK.Name then
                    u:Create(
                        aK,
                        TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                        {BackgroundColor3 = Color3.fromRGB(47, 49, 54)}
                    ):Play()
                    u:Create(
                        aL,
                        TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                        {CornerRadius = UDim.new(1, 0)}
                    ):Play()
                    aN:TweenSize(UDim2.new(0, 11, 0, 10), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
                end
            end
        )
        aK.MouseButton1Click:Connect(
            function()
                X = aK.Name
                for l, m in next, a7:GetChildren() do
                    if m.Name == "ServerFrame" then
                        m.Visible = false
                    end
                    aP.Visible = true
                end
                for l, m in next, ai:GetChildren() do
                    if m.ClassName == "TextButton" then
                        u:Create(
                            m,
                            TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                            {BackgroundColor3 = Color3.fromRGB(47, 49, 54)}
                        ):Play()
                        u:Create(
                            aK,
                            TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                            {BackgroundColor3 = Color3.fromRGB(23, 23, 23)}
                        ):Play()
                        u:Create(
                            m.ServerCorner,
                            TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                            {CornerRadius = UDim.new(1, 0)}
                        ):Play()
                        u:Create(
                            aL,
                            TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                            {CornerRadius = UDim.new(0, 15)}
                        ):Play()
                        m.ServerWhiteFrame:TweenSize(
                            UDim2.new(0, 11, 0, 10),
                            Enum.EasingDirection.Out,
                            Enum.EasingStyle.Quart,
                            .3,
                            true
                        )
                        aN:TweenSize(
                            UDim2.new(0, 11, 0, 46),
                            Enum.EasingDirection.Out,
                            Enum.EasingStyle.Quart,
                            .3,
                            true
                        )
                    end
                end
            end
        )
        if aH == "" then
            aK.Text = string.sub(S, 1, 1)
        else
            aM.Image = aH
        end
        if Z == false then
            u:Create(
                aK,
                TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                {BackgroundColor3 = Color3.fromRGB(23, 23, 23)}
            ):Play()
            u:Create(
                aL,
                TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                {CornerRadius = UDim.new(0, 15)}
            ):Play()
            aN:TweenSize(UDim2.new(0, 11, 0, 46), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, .3, true)
            aP.Visible = true
            aK.Name = S .. "Server"
            X = aK.Name
            Z = true
        end
        local b6 = {}
        function b6:Channel(S, b7)
            local b8 = b7 or ""
            local b9 = Instance.new("ImageLabel")
            local ba = Instance.new("Frame")
            local bb = Instance.new("UICorner")
            local bc = Instance.new("TextButton")
            local bd = Instance.new("UICorner")
            local be = Instance.new("TextLabel")
            local bf = Instance.new("TextLabel")
            ba.Name = S .. "ChannelBtn"
            ba.Parent = b0
            ba.Position = UDim2.new(0.24118948, 0, 0.578947365, 0)
            ba.Size = UDim2.new(0, 162, 0, 32)
            ba.BackgroundColor3 = V
            bb.CornerRadius = UDim.new(0, 6)
            bb.Name = "ChannelBtnOutlineCorner"
            bb.Parent = ba
            bc.Name = S .. "ChannelBtn"
            bc.Parent = ba
            bc.BackgroundColor3 = Color3.fromRGB(27, 27, 27)
            bc.BorderSizePixel = 0
            bc.Position = UDim2.new(0.002761, 0, 0.02761, 0)
            bc.Size = UDim2.new(0, 160, 0, 30)
            bc.AutoButtonColor = false
            bc.Font = Enum.Font.SourceSans
            bc.Text = ""
            bc.TextColor3 = Color3.fromRGB(0, 0, 0)
            bc.TextSize = 14.000
            bd.CornerRadius = UDim.new(0, 6)
            bd.Name = "ChannelBtnCorner"
            bd.Parent = bc
            b9.Name = "TabIcon"
            b9.Parent = bc
            b9.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            b9.BackgroundTransparency = 1.000
            b9.Position = UDim2.new(0.0234146333, 0, 0.12, 0)
            b9.Size = UDim2.new(0, 20, 0, 20)
            b9.Image = b8
            b9.ImageTransparency = 0
            bf.Name = "ChannelBtnTitle"
            bf.Parent = bc
            bf.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            bf.BackgroundTransparency = 1.000
            bf.BorderSizePixel = 0
            bf.Position = UDim2.new(0.163747092, 0, -0.166666672, 0)
            bf.Size = UDim2.new(0, 95, 0, 39)
            bf.Font = Enum.Font.Gotham
            bf.Text = S
            bf.TextColor3 = V
            bf.TextSize = 14.000
            bf.TextXAlignment = Enum.TextXAlignment.Left
            b0.CanvasSize = UDim2.new(0, 0, 0, b1.AbsoluteContentSize.Y)
            local bg = Instance.new("ScrollingFrame")
            local bh = Instance.new("UIListLayout")
            bg.Name = "ChannelHolder"
            bg.Parent = aY
            bg.Active = true
            bg.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
            bg.BackgroundTransparency = 1.000
            bg.BorderSizePixel = 0
            bg.Position = UDim2.new(0.0360843192, 0, 0.0241984241, 0)
            bg.Size = UDim2.new(0, 412, 0, 314)
            bg.ScrollBarThickness = 6
            bg.CanvasSize = UDim2.new(0, 0, 0, 0)
            bg.ScrollBarImageTransparency = 0
            bg.ScrollBarImageColor3 = V
            bg.Visible = false
            bg.ClipsDescendants = false
            bh.Name = "ChannelHolderLayout"
            bh.Parent = bg
            bh.SortOrder = Enum.SortOrder.LayoutOrder
            bh.Padding = UDim.new(0, 6)
            bc.MouseEnter:Connect(
                function()
                    if aJ ~= bc.Name then
                        bc.BackgroundColor3 = V
                        bf.TextColor3 = Color3.fromRGB(27, 27, 27)
                    end
                end
            )
            bc.MouseLeave:Connect(
                function()
                    if aJ ~= bc.Name then
                        bc.BackgroundColor3 = Color3.fromRGB(27, 27, 27)
                        bf.TextColor3 = V
                    end
                end
            )
            bc.MouseEnter:Connect(
                function()
                    if aJ == bc.Name then
                        bc.BackgroundColor3 = V
                        bf.TextColor3 = Color3.fromRGB(27, 27, 27)
                    end
                end
            )
            bc.MouseLeave:Connect(
                function()
                    if aJ == bc.Name then
                        bc.BackgroundColor3 = Color3.fromRGB(27, 27, 27)
                        bf.TextColor3 = V
                    end
                end
            )
            bc.MouseButton1Click:Connect(
                function()
                    for l, m in next, aY:GetChildren() do
                        if m.Name == "ChannelHolder" then
                            m.Visible = false
                        end
                        bg.Visible = true
                    end
                    for l, m in next, b0:GetChildren() do
                        if m.ClassName == "TextButton" then
                            m.BackgroundColor3 = Color3.fromRGB(27, 27, 27)
                            m.ChannelBtnTitle.TextColor3 = V
                        end
                        aP.Visible = true
                    end
                    aX.Text = S
                    bc.BackgroundColor3 = Color3.fromRGB(27, 27, 27)
                    bf.TextColor3 = V
                    aJ = bc.Name
                end
            )
            if aI == false then
                aI = true
                aX.Text = S
                bc.BackgroundColor3 = Color3.fromRGB(27, 27, 27)
                bf.TextColor3 = V
                aJ = bc.Name
                bg.Visible = true
            end
            local bi = {}
            function bi:Button(S, bj)
                local bk = Instance.new("TextButton")
                local bl = Instance.new("UICorner")
                bk.Name = "Button"
                bk.Parent = bg
                bk.BackgroundColor3 = Color3.fromRGB(23, 23, 23)
                bk.Size = UDim2.new(0, 401, 0, 30)
                bk.AutoButtonColor = false
                bk.Font = Enum.Font.Gotham
                bk.TextColor3 = V
                bk.TextSize = 14.000
                bk.Text = S
                bl.CornerRadius = UDim.new(0, 4)
                bl.Name = "ButtonCorner"
                bl.Parent = bk
                bk.MouseEnter:Connect(
                    function()
                        u:Create(
                            bk,
                            TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                            {BackgroundColor3 = V, TextColor3 = Color3.fromRGB(23, 23, 23)}
                        ):Play()
                    end
                )
                bk.MouseButton1Click:Connect(
                    function()
                        pcall(bj)
                        bk.TextSize = 0
                        u:Create(
                            bk,
                            TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                            {TextSize = 14}
                        ):Play()
                    end
                )
                bk.MouseLeave:Connect(
                    function()
                        u:Create(
                            bk,
                            TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                            {BackgroundColor3 = Color3.fromRGB(23, 23, 23), TextColor3 = V}
                        ):Play()
                    end
                )
                bg.CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)
            end
            function bi:Toggle(S, bm, bj)
                local bn = false
                local bo = Instance.new("TextButton")
                local bp = Instance.new("TextLabel")
                local bq = Instance.new("Frame")
                local br = Instance.new("UICorner")
                local bs = Instance.new("Frame")
                local bt = Instance.new("UICorner")
                local bu = Instance.new("Frame")
                local bv = Instance.new("UICorner")
                local b8 = Instance.new("ImageLabel")
                bo.Name = "Toggle"
                bo.Parent = bg
                bo.BackgroundColor3 = Color3.fromRGB(23, 23, 23)
                bo.BorderSizePixel = 0
                bo.Position = UDim2.new(0.261979163, 0, 0.190789461, 0)
                bo.Size = UDim2.new(0, 401, 0, 30)
                bo.AutoButtonColor = false
                bo.Font = Enum.Font.Gotham
                bo.Text = ""
                bo.TextColor3 = Color3.fromRGB(255, 255, 255)
                bo.TextSize = 14.000
                bp.Name = "ToggleTitle"
                bp.Parent = bo
                bp.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                bp.BackgroundTransparency = 1.000
                bp.Position = UDim2.new(0, 5, 0, 0)
                bp.Size = UDim2.new(0, 200, 0, 30)
                bp.Font = Enum.Font.Gotham
                bp.Text = S
                bp.TextColor3 = V
                bp.TextSize = 14.000
                bp.TextXAlignment = Enum.TextXAlignment.Left
                bu.Name = "ToggleFrameOutline"
                bu.Parent = bo
                bu.BackgroundColor3 = V
                bu.Position = UDim2.new(0.900481343, -5, 0.16300018, 0)
                bu.Size = UDim2.new(0, 41, 0, 22)
                bv.CornerRadius = UDim.new(1, 8)
                bv.Name = "ToggleFrameOutlineCorner"
                bv.Parent = bu
                bq.Name = "ToggleFrame"
                bq.Parent = bu
                bq.BackgroundColor3 = Color3.fromRGB(31, 31, 31)
                bq.Size = UDim2.new(0, 39, 0, 20)
                bq.Position = UDim2.new(0, 1, 0.03761, 0)
                br.CornerRadius = UDim.new(1, 8)
                br.Name = "ToggleFrameCorner"
                br.Parent = bq
                bs.Name = "ToggleFrameCircle"
                bs.Parent = bq
                bs.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                bs.Position = UDim2.new(0.234999999, -5, 0.133000001, 0)
                bs.Size = UDim2.new(0, 15, 0, 15)
                bt.CornerRadius = UDim.new(1, 0)
                bt.Name = "ToggleFrameCircleCorner"
                bt.Parent = bs
                b8.Name = "Icon"
                b8.Parent = bs
                b8.AnchorPoint = Vector2.new(0.5, 0.5)
                b8.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                b8.BackgroundTransparency = 1.000
                b8.BorderColor3 = Color3.fromRGB(27, 42, 53)
                b8.Position = UDim2.new(0, 8, 0, 8)
                b8.Size = UDim2.new(0, 13, 0, 13)
                b8.Image = "http://www.roblox.com/asset/?id=6035047409"
                b8.ImageColor3 = Color3.fromRGB(31, 31, 31)
                if bm == true then
                    u:Create(b8, TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = V}):Play(

                    )
                    u:Create(
                        bq,
                        TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                        {BackgroundColor3 = V}
                    ):Play()
                    bs:TweenPosition(
                        UDim2.new(0.655, -5, 0.133000001, 0),
                        Enum.EasingDirection.Out,
                        Enum.EasingStyle.Quart,
                        .3,
                        true
                    )
                    u:Create(
                        b8,
                        TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                        {ImageTransparency = 1}
                    ):Play()
                    b8.Image = "http://www.roblox.com/asset/?id=6023426926"
                    wait(.1)
                    u:Create(
                        b8,
                        TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                        {ImageTransparency = 0}
                    ):Play()
                    bn = not bn
                    pcall(bj, bn)
                end
                bo.MouseButton1Click:Connect(
                    function()
                        if bn == false then
                            u:Create(
                                b8,
                                TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                                {ImageColor3 = V}
                            ):Play()
                            u:Create(
                                bq,
                                TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                                {BackgroundColor3 = Color3.fromRGB(0, 255, 136)}
                            ):Play()
                            bs:TweenPosition(
                                UDim2.new(0.655, -5, 0.133000001, 0),
                                Enum.EasingDirection.Out,
                                Enum.EasingStyle.Quart,
                                .3,
                                true
                            )
                            u:Create(
                                b8,
                                TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                                {ImageTransparency = 1}
                            ):Play()
                            b8.Image = "http://www.roblox.com/asset/?id=6023426926"
                            wait(.1)
                            u:Create(
                                b8,
                                TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                                {ImageTransparency = 0}
                            ):Play()
                        else
                            u:Create(
                                b8,
                                TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                                {ImageColor3 = Color3.fromRGB(31, 31, 31)}
                            ):Play()
                            u:Create(
                                bq,
                                TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                                {BackgroundColor3 = Color3.fromRGB(255, 0, 0)}
                            ):Play()
                            bs:TweenPosition(
                                UDim2.new(0.234999999, -5, 0.133000001, 0),
                                Enum.EasingDirection.Out,
                                Enum.EasingStyle.Quart,
                                .3,
                                true
                            )
                            u:Create(
                                b8,
                                TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                                {ImageTransparency = 1}
                            ):Play()
                            b8.Image = "http://www.roblox.com/asset/?id=6035047409"
                            wait(.1)
                            u:Create(
                                b8,
                                TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                                {ImageTransparency = 0}
                            ):Play()
                        end
                        bn = not bn
                        pcall(bj, bn)
                    end
                )
                bg.CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)
            end
            function bi:Slider(S, bw, bx, by, bj)
                local bz = {}
                local bA = false
                local bB = Instance.new("TextButton")
                local bC = Instance.new("TextLabel")
                local bD = Instance.new("Frame")
                local bE = Instance.new("UICorner")
                local bF = Instance.new("Frame")
                local bG = Instance.new("UICorner")
                local bH = Instance.new("Frame")
                local bI = Instance.new("UICorner")
                local bJ = Instance.new("Frame")
                local bK = Instance.new("UICorner")
                local bL = Instance.new("Frame")
                local bM = Instance.new("ImageLabel")
                local bN = Instance.new("TextLabel")
                bB.Name = "Slider"
                bB.Parent = bg
                bB.BackgroundColor3 = Color3.fromRGB(23, 23, 23)
                bB.BorderSizePixel = 0
                bB.Position = UDim2.new(0, 0, 0.216560602, 0)
                bB.Size = UDim2.new(0, 401, 0, 38)
                bB.AutoButtonColor = false
                bB.Font = Enum.Font.Gotham
                bB.Text = ""
                bB.TextColor3 = Color3.fromRGB(255, 255, 255)
                bB.TextSize = 14.000
                bC.Name = "SliderTitle"
                bC.Parent = bB
                bC.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                bC.BackgroundTransparency = 1.000
                bC.Position = UDim2.new(0, 5, 0, -4)
                bC.Size = UDim2.new(0, 200, 0, 27)
                bC.Font = Enum.Font.Gotham
                bC.Text = S
                bC.TextColor3 = V
                bC.TextSize = 14.000
                bC.TextXAlignment = Enum.TextXAlignment.Left
                bD.Name = "SliderFrame"
                bD.Parent = bB
                bD.AnchorPoint = Vector2.new(0.5, 0.5)
                bD.BackgroundColor3 = Color3.fromRGB(79, 84, 92)
                bD.Position = UDim2.new(0.497999996, 0, 0.757000029, 0)
                bD.Size = UDim2.new(0, 385, 0, 8)
                bE.Name = "SliderFrameCorner"
                bE.Parent = bD
                bF.Name = "CurrentValueFrame"
                bF.Parent = bD
                bF.BackgroundColor3 = V
                bF.Size = UDim2.new((by or 0) / bx, 0, 0, 8)
                bG.Name = "CurrentValueFrameCorner"
                bG.Parent = bF
                bH.Name = "Zip"
                bH.Parent = bD
                bH.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                bH.Position = UDim2.new((by or 0) / bx, -6, -0.644999981, 0)
                bH.Size = UDim2.new(0, 10, 0, 18)
                bI.CornerRadius = UDim.new(0, 3)
                bI.Name = "ZipCorner"
                bI.Parent = bH
                bJ.Name = "ValueBubble"
                bJ.Parent = bH
                bJ.AnchorPoint = Vector2.new(0.5, 0.5)
                bJ.BackgroundColor3 = Color3.fromRGB(38, 38, 38)
                bJ.Position = UDim2.new(0.5, 0, -1.00800002, 0)
                bJ.Size = UDim2.new(0, 36, 0, 21)
                bJ.Visible = false
                bH.MouseEnter:Connect(
                    function()
                        if bA == false then
                            bJ.Visible = true
                        end
                    end
                )
                bH.MouseLeave:Connect(
                    function()
                        if bA == false then
                            bJ.Visible = false
                        end
                    end
                )
                bK.CornerRadius = UDim.new(0, 3)
                bK.Name = "ValueBubbleCorner"
                bK.Parent = bJ
                bL.Name = "SquareBubble"
                bL.Parent = bJ
                bL.AnchorPoint = Vector2.new(0.5, 0.5)
                bL.BackgroundColor3 = Color3.fromRGB(38, 38, 38)
                bL.BorderSizePixel = 0
                bL.Position = UDim2.new(0.493000001, 0, 0.637999971, 0)
                bL.Rotation = 45.000
                bL.Size = UDim2.new(0, 19, 0, 19)
                bM.Name = "GlowBubble"
                bM.Parent = bJ
                bM.BackgroundColor3 = V
                bM.BackgroundTransparency = 1.000
                bM.BorderSizePixel = 0
                bM.Position = UDim2.new(0, -15, 0, -15)
                bM.Size = UDim2.new(1, 30, 1, 30)
                bM.ZIndex = 0
                bM.Image = "rbxassetid://4996891970"
                bM.ImageColor3 = Color3.fromRGB(15, 15, 15)
                bM.ScaleType = Enum.ScaleType.Slice
                bM.SliceCenter = Rect.new(20, 20, 280, 280)
                bN.Name = "ValueLabel"
                bN.Parent = bJ
                bN.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                bN.BackgroundTransparency = 1.000
                bN.Size = UDim2.new(0, 36, 0, 21)
                bN.Font = Enum.Font.Gotham
                bN.Text = tostring(by and math.floor(by / bx * (bx - bw) + bw) or 0)
                bN.TextColor3 = V
                bN.TextSize = 10.000
                local function bO(L)
                    local N =
                        UDim2.new(
                        math.clamp((L.Position.X - bD.AbsolutePosition.X) / bD.AbsoluteSize.X, 0, 1),
                        -6,
                        -0.644999981,
                        0
                    )
                    local bP =
                        UDim2.new(math.clamp((L.Position.X - bD.AbsolutePosition.X) / bD.AbsoluteSize.X, 0, 1), 0, 0, 8)
                    bF.Size = bP
                    bH.Position = N
                    local bQ = math.floor(N.X.Scale * bx / bx * (bx - bw) + bw)
                    bN.Text = tostring(bQ)
                    pcall(bj, bQ)
                end
                bH.InputBegan:Connect(
                    function(L)
                        if L.UserInputType == Enum.UserInputType.MouseButton1 then
                            bA = true
                            bJ.Visible = true
                        end
                    end
                )
                bH.InputEnded:Connect(
                    function(L)
                        if L.UserInputType == Enum.UserInputType.MouseButton1 then
                            bA = false
                            bJ.Visible = false
                        end
                    end
                )
                game:GetService("UserInputService").InputChanged:Connect(
                    function(L)
                        if bA and L.UserInputType == Enum.UserInputType.MouseMovement then
                            bO(L)
                        end
                    end
                )
                function bz:Change(bR)
                    bF.Size = UDim2.new((bR or 0) / bx, 0, 0, 8)
                    bH.Position = UDim2.new((bR or 0) / bx, -6, -0.644999981, 0)
                    bN.Text = tostring(bR and math.floor(bR / bx * (bx - bw) + bw) or 0)
                    pcall(bj, bR)
                end
                bg.CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)
                return bz
            end
            function bi:Line()
                local bS = Instance.new("Frame")
                local bT = Instance.new("Frame")
                bS.Name = "Line1"
                bS.Parent = bg
                bS.BackgroundColor3 = V
                bS.BackgroundTransparency = 1.000
                bS.Position = UDim2.new(0, 0, 0.350318581, 0)
                bS.Size = UDim2.new(0, 100, 0, 8)
                bT.Name = "Line2"
                bT.Parent = bS
                bT.BackgroundColor3 = V
                bT.BorderSizePixel = 0
                bT.Position = UDim2.new(0, 0, 0, 4)
                bT.Size = UDim2.new(0, 401, 0, 1)
                bg.CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)
            end
            function bi:Dropdown(S, bU, bj)
                local bV = {}
                local bW = 0
                local bX = 0
                local bY = false
                local bZ = Instance.new("Frame")
                local b_ = Instance.new("TextLabel")
                local c0 = Instance.new("Frame")
                local c1 = Instance.new("UICorner")
                local c2 = Instance.new("Frame")
                local c3 = Instance.new("UICorner")
                local c4 = Instance.new("TextLabel")
                local c5 = Instance.new("ImageLabel")
                local c6 = Instance.new("TextButton")
                bZ.Name = "Dropdown"
                bZ.Parent = bg
                bZ.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                bZ.BackgroundTransparency = 1.000
                bZ.Position = UDim2.new(0.0796874985, 0, 0.445175439, 0)
                bZ.Size = UDim2.new(0, 403, 0, 60)
                b_.Name = "DropdownTitle"
                b_.Parent = bZ
                b_.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                b_.BackgroundTransparency = 1.000
                b_.Position = UDim2.new(0, 5, 0, 0)
                b_.Size = UDim2.new(0, 200, 0, 29)
                b_.Font = Enum.Font.Gotham
                b_.Text = ""
                b_.TextColor3 = V
                b_.TextSize = 14.000
                b_.TextXAlignment = Enum.TextXAlignment.Left
                c0.Name = "DropdownFrameOutline"
                c0.Parent = b_
                c0.AnchorPoint = Vector2.new(0.5, 0.5)
                c0.BackgroundColor3 = V
                c0.Position = UDim2.new(0.988442957, 0, 1.0197437, 0)
                c0.Size = UDim2.new(0, 396, 0, 36)
                c1.CornerRadius = UDim.new(0, 3)
                c1.Name = "DropdownFrameOutlineCorner"
                c1.Parent = c0
                c2.Name = "DropdownFrame"
                c2.Parent = b_
                c2.BackgroundColor3 = Color3.fromRGB(23, 23, 23)
                c2.ClipsDescendants = true
                c2.Position = UDim2.new(0.00899999978, 0, 0.46638527, 0)
                c2.Selectable = true
                c2.Size = UDim2.new(0, 392, 0, 32)
                c3.CornerRadius = UDim.new(0, 3)
                c3.Name = "DropdownFrameCorner"
                c3.Parent = c2
                c4.Name = "CurrentSelectedText"
                c4.Parent = c2
                c4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                c4.BackgroundTransparency = 1.000
                c4.Position = UDim2.new(0.0178571437, 0, 0, 0)
                c4.Size = UDim2.new(0, 193, 0, 32)
                c4.Font = Enum.Font.Gotham
                c4.Text = S
                c4.TextTransparency = 0.250
                c4.TextColor3 = V
                c4.TextSize = 14.000
                c4.TextXAlignment = Enum.TextXAlignment.Left
                c5.Name = "ArrowImg"
                c5.Parent = c4
                c5.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                c5.BackgroundTransparency = 1.000
                c5.Position = UDim2.new(1.84974098, 0, 0.167428851, 0)
                c5.Size = UDim2.new(0, 22, 0, 22)
                c5.Image = "http://www.roblox.com/asset/?id=6034818372"
                c5.ImageColor3 = V
                c6.Name = "DropdownFrameBtn"
                c6.Parent = c2
                c6.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                c6.BackgroundTransparency = 1.000
                c6.Size = UDim2.new(0, 392, 0, 32)
                c6.Font = Enum.Font.SourceSans
                c6.Text = ""
                c6.TextColor3 = Color3.fromRGB(0, 0, 0)
                c6.TextSize = 14.000
                local c7 = Instance.new("Frame")
                local c8 = Instance.new("UICorner")
                local c9 = Instance.new("Frame")
                local ca = Instance.new("UICorner")
                local cb = Instance.new("TextLabel")
                local cc = Instance.new("ScrollingFrame")
                local cd = Instance.new("UIListLayout")
                c7.Name = "DropdownFrameMainOutline"
                c7.Parent = b_
                c7.BackgroundColor3 = V
                c7.Position = UDim2.new(-0.00155700743, 0, 1.66983342, 0)
                c7.Size = UDim2.new(0, 396, 0, 81)
                c7.Visible = false
                c8.CornerRadius = UDim.new(0, 3)
                c8.Name = "DropdownFrameMainOutlineCorner"
                c8.Parent = c7
                c9.Name = "DropdownFrameMain"
                c9.Parent = b_
                c9.BackgroundColor3 = Color3.fromRGB(23, 23, 23)
                c9.ClipsDescendants = true
                c9.Position = UDim2.new(0.00799999978, 0, 1.7468965, 0)
                c9.Selectable = true
                c9.Size = UDim2.new(0, 392, 0, 77)
                c9.Visible = false
                ca.CornerRadius = UDim.new(0, 3)
                ca.Name = "DropdownFrameMainCorner"
                ca.Parent = c9
                cb.Name = "ItemHolderLabel"
                cb.Parent = c9
                cb.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                cb.BackgroundTransparency = 1.000
                cb.Position = UDim2.new(0.0178571437, 0, 0, 0)
                cb.Size = UDim2.new(0, 193, 0, 13)
                cb.Font = Enum.Font.Gotham
                cb.Text = ""
                cb.TextColor3 = V
                cb.TextSize = 14.000
                cb.TextXAlignment = Enum.TextXAlignment.Left
                cc.Name = "ItemHolder"
                cc.Parent = cb
                cc.Active = true
                cc.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                cc.BackgroundTransparency = 1.000
                cc.Position = UDim2.new(0, 0, 0.215384638, 0)
                cc.Size = UDim2.new(0, 385, 0, 0)
                cc.CanvasSize = UDim2.new(0, 0, 0, 0)
                cc.ScrollBarThickness = 6
                cc.BorderSizePixel = 0
                cc.ScrollBarImageColor3 = V
                cd.Name = "ItemHolderLayout"
                cd.Parent = cc
                cd.SortOrder = Enum.SortOrder.LayoutOrder
                cd.Padding = UDim.new(0, 0)
                c6.MouseButton1Click:Connect(
                    function()
                        if bY == false then
                            c9.Visible = true
                            c7.Visible = true
                            u:Create(
                                bZ,
                                TweenInfo.new(.5, Enum.EasingStyle.Quart),
                                {Size = UDim2.new(0, 403, 0, 60 + c7.AbsoluteSize.Y)}
                            ):Play()
                            u:Create(
                                bg,
                                TweenInfo.new(.5, Enum.EasingStyle.Quart),
                                {CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)}
                            ):Play()
                        else
                            c9.Visible = false
                            c7.Visible = false
                            u:Create(bZ, TweenInfo.new(.5, Enum.EasingStyle.Quart), {Size = UDim2.new(0, 403, 0, 60)}):Play(

                            )
                            u:Create(
                                bg,
                                TweenInfo.new(.5, Enum.EasingStyle.Quart),
                                {CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)}
                            ):Play()
                            wait(.2)
                        end
                        bY = not bY
                    end
                )
                for l, m in next, bU do
                    bW = bW + 1
                    if bW == 1 then
                        bX = 29
                    elseif bW == 2 then
                        bX = 58
                    elseif bW >= 3 then
                        bX = 87
                    end
                    local ce = Instance.new("TextButton")
                    local cf = Instance.new("UICorner")
                    local cg = Instance.new("TextLabel")
                    ce.Name = "Item"
                    ce.Parent = cc
                    ce.BackgroundColor3 = Color3.fromRGB(42, 44, 48)
                    ce.Size = UDim2.new(0, 379, 0, 29)
                    ce.AutoButtonColor = false
                    ce.Font = Enum.Font.SourceSans
                    ce.Text = ""
                    ce.TextColor3 = Color3.fromRGB(0, 0, 0)
                    ce.TextSize = 14.000
                    ce.BackgroundTransparency = 1
                    cf.CornerRadius = UDim.new(0, 4)
                    cf.Name = "ItemCorner"
                    cf.Parent = ce
                    cg.Name = "ItemText"
                    cg.Parent = ce
                    cg.BackgroundColor3 = Color3.fromRGB(42, 44, 48)
                    cg.BackgroundTransparency = 1.000
                    cg.Position = UDim2.new(0.0211081803, 0, 0, 0)
                    cg.Size = UDim2.new(0, 192, 0, 29)
                    cg.Font = Enum.Font.Gotham
                    cg.TextColor3 = V
                    cg.TextSize = 14.000
                    cg.TextXAlignment = Enum.TextXAlignment.Left
                    cg.Text = m
                    ce.MouseEnter:Connect(
                        function()
                            cg.TextColor3 = Color3.fromRGB(255, 255, 255)
                            ce.BackgroundTransparency = 0
                        end
                    )
                    ce.MouseLeave:Connect(
                        function()
                            cg.TextColor3 = V
                            ce.BackgroundTransparency = 1
                        end
                    )
                    ce.MouseButton1Click:Connect(
                        function()
                            c4.Text = m
                            c4.TextTransparency = 0.250
                            pcall(bj, m)
                            c9.Visible = false
                            c7.Visible = false
                            u:Create(bZ, TweenInfo.new(.5, Enum.EasingStyle.Quart), {Size = UDim2.new(0, 403, 0, 60)}):Play(

                            )
                            u:Create(
                                bg,
                                TweenInfo.new(.5, Enum.EasingStyle.Quart),
                                {CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)}
                            ):Play()
                            wait(.2)
                            bY = not bY
                        end
                    )
                    cc.CanvasSize = UDim2.new(0, 0, 0, cd.AbsoluteContentSize.Y)
                    cc.Size = UDim2.new(0, 385, 0, bX)
                    c9.Size = UDim2.new(0, 392, 0, bX + 6)
                    c7.Size = UDim2.new(0, 396, 0, bX + 10)
                end
                bg.CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)
                function bV:Clear()
                    for l, m in next, cc:GetChildren() do
                        if m.Name == "Item" then
                            m:Destroy()
                        end
                    end
                    c4.Text = S
                    c4.TextTransparency = 0.250
                    bW = 0
                    bX = 0
                    cc.Size = UDim2.new(0, 385, 0, 0)
                    c9.Size = UDim2.new(0, 392, 0, 0)
                    c7.Size = UDim2.new(0, 396, 0, 0)
                    bZ.Size = UDim2.new(0, 403, 0, 60)
                    c9.Visible = false
                    c7.Visible = false
                    bg.CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)
                end
                function bV:Add(ch)
                    bW = bW + 1
                    if bW == 1 then
                        bX = 29
                    elseif bW == 2 then
                        bX = 58
                    elseif bW >= 3 then
                        bX = 87
                    end
                    local ce = Instance.new("TextButton")
                    local cf = Instance.new("UICorner")
                    local cg = Instance.new("TextLabel")
                    ce.Name = "Item"
                    ce.Parent = cc
                    ce.BackgroundColor3 = Color3.fromRGB(42, 44, 48)
                    ce.Size = UDim2.new(0, 379, 0, 29)
                    ce.AutoButtonColor = false
                    ce.Font = Enum.Font.SourceSans
                    ce.Text = ""
                    ce.TextColor3 = Color3.fromRGB(0, 0, 0)
                    ce.TextSize = 14.000
                    ce.BackgroundTransparency = 1
                    cf.CornerRadius = UDim.new(0, 4)
                    cf.Name = "ItemCorner"
                    cf.Parent = ce
                    cg.Name = "ItemText"
                    cg.Parent = ce
                    cg.BackgroundColor3 = Color3.fromRGB(42, 44, 48)
                    cg.BackgroundTransparency = 1.000
                    cg.Position = UDim2.new(0.0211081803, 0, 0, 0)
                    cg.Size = UDim2.new(0, 192, 0, 29)
                    cg.Font = Enum.Font.Gotham
                    cg.TextColor3 = V
                    cg.TextSize = 14.000
                    cg.TextXAlignment = Enum.TextXAlignment.Left
                    cg.Text = ch
                    ce.MouseEnter:Connect(
                        function()
                            cg.TextColor3 = Color3.fromRGB(255, 255, 255)
                            ce.BackgroundTransparency = 0
                        end
                    )
                    ce.MouseLeave:Connect(
                        function()
                            cg.TextColor3 = V
                            ce.BackgroundTransparency = 1
                        end
                    )
                    ce.MouseButton1Click:Connect(
                        function()
                            c4.Text = ch
                            c4.TextTransparency = 0.250
                            pcall(bj, ch)
                            c9.Visible = false
                            c7.Visible = false
                            u:Create(bZ, TweenInfo.new(.5, Enum.EasingStyle.Quart), {Size = UDim2.new(0, 403, 0, 60)}):Play(

                            )
                            u:Create(
                                bg,
                                TweenInfo.new(.5, Enum.EasingStyle.Quart),
                                {CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)}
                            ):Play()
                            wait(.2)
                            bY = not bY
                        end
                    )
                    cc.CanvasSize = UDim2.new(0, 0, 0, cd.AbsoluteContentSize.Y)
                    cc.Size = UDim2.new(0, 385, 0, bX)
                    c9.Size = UDim2.new(0, 392, 0, bX + 6)
                    c7.Size = UDim2.new(0, 396, 0, bX + 10)
                end
                return bV
            end
            function bi:Colorpicker(S, ci, bj)
                local cj = Color3.fromRGB(0, 0, 0)
                local ck = Color3.fromRGB(0, 0, 0)
                local cl = nil
                local cm = nil
                local cn, co, cp = 1, 1, 1
                local cq = false
                local cr = nil
                local cs = nil
                local ct = nil
                local cu = Instance.new("Frame")
                local cv = Instance.new("TextLabel")
                local cw = Instance.new("Frame")
                local cx = Instance.new("UICorner")
                local cy = Instance.new("Frame")
                local cz = Instance.new("UICorner")
                local cA = Instance.new("ImageLabel")
                local cB = Instance.new("UICorner")
                local cC = Instance.new("ImageLabel")
                local cD = Instance.new("ImageLabel")
                local cE = Instance.new("UICorner")
                local cF = Instance.new("UIGradient")
                local cG = Instance.new("ImageLabel")
                local cH = Instance.new("Frame")
                local cI = Instance.new("UICorner")
                cu.Name = "Colorpicker"
                cu.Parent = bg
                cu.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                cu.BackgroundTransparency = 1.000
                cu.Position = UDim2.new(0.0895741582, 0, 0.474232763, 0)
                cu.Size = UDim2.new(0, 403, 0, 175)
                cv.Name = "ColorpickerTitle"
                cv.Parent = cu
                cv.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                cv.BackgroundTransparency = 1.000
                cv.Position = UDim2.new(0, 5, 0, 0)
                cv.Size = UDim2.new(0, 200, 0, 29)
                cv.Font = Enum.Font.Gotham
                cv.Text = "Colorpicker"
                cv.TextColor3 = V
                cv.TextSize = 14.000
                cv.TextXAlignment = Enum.TextXAlignment.Left
                cw.Name = "ColorpickerFrameOutline"
                cw.Parent = cv
                cw.BackgroundColor3 = V
                cw.Position = UDim2.new(-0.00100000005, 0, 0.991999984, 0)
                cw.Size = UDim2.new(0, 238, 0, 139)
                cx.CornerRadius = UDim.new(0, 3)
                cx.Name = "ColorpickerFrameOutlineCorner"
                cx.Parent = cw
                cy.Name = "ColorpickerFrame"
                cy.Parent = cv
                cy.BackgroundColor3 = Color3.fromRGB(23, 23, 23)
                cy.ClipsDescendants = true
                cy.Position = UDim2.new(0.00899999978, 0, 1.06638515, 0)
                cy.Selectable = true
                cy.Size = UDim2.new(0, 234, 0, 135)
                cz.CornerRadius = UDim.new(0, 3)
                cz.Name = "ColorpickerFrameCorner"
                cz.Parent = cy
                cA.Name = "Color"
                cA.Parent = cy
                cA.BackgroundColor3 = Color3.fromRGB(255, 0, 4)
                cA.Position = UDim2.new(0, 10, 0, 10)
                cA.Size = UDim2.new(0, 154, 0, 118)
                cA.ZIndex = 10
                cA.Image = "rbxassetid://4155801252"
                cB.CornerRadius = UDim.new(0, 3)
                cB.Name = "ColorCorner"
                cB.Parent = cA
                cC.Name = "ColorSelection"
                cC.Parent = cA
                cC.AnchorPoint = Vector2.new(0.5, 0.5)
                cC.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                cC.BackgroundTransparency = 1.000
                cC.Position = UDim2.new(ci and select(3, Color3.toHSV(ci)))
                cC.Size = UDim2.new(0, 18, 0, 18)
                cC.Image = "http://www.roblox.com/asset/?id=4805639000"
                cC.ScaleType = Enum.ScaleType.Fit
                cD.Name = "Hue"
                cD.Parent = cy
                cD.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                cD.Position = UDim2.new(0, 171, 0, 10)
                cD.Size = UDim2.new(0, 18, 0, 118)
                cE.CornerRadius = UDim.new(0, 3)
                cE.Name = "HueCorner"
                cE.Parent = cD
                cF.Color =
                    ColorSequence.new {
                    ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 0, 4)),
                    ColorSequenceKeypoint.new(0.20, Color3.fromRGB(234, 255, 0)),
                    ColorSequenceKeypoint.new(0.40, Color3.fromRGB(21, 255, 0)),
                    ColorSequenceKeypoint.new(0.60, Color3.fromRGB(0, 255, 255)),
                    ColorSequenceKeypoint.new(0.80, Color3.fromRGB(0, 17, 255)),
                    ColorSequenceKeypoint.new(0.90, Color3.fromRGB(255, 0, 251)),
                    ColorSequenceKeypoint.new(1.00, Color3.fromRGB(255, 0, 4))
                }
                cF.Rotation = 270
                cF.Name = "HueGradient"
                cF.Parent = cD
                cG.Name = "HueSelection"
                cG.Parent = cD
                cG.AnchorPoint = Vector2.new(0.5, 0.5)
                cG.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                cG.BackgroundTransparency = 1.000
                cG.Position = UDim2.new(0.48, 0, 1 - select(1, Color3.toHSV(ci)))
                cG.Size = UDim2.new(0, 18, 0, 18)
                cG.Image = "http://www.roblox.com/asset/?id=4805639000"
                cH.Name = "PresetClr"
                cH.Parent = cy
                cH.BackgroundColor3 = ci
                cH.Position = UDim2.new(0.846153855, 0, 0.0740740746, 0)
                cH.Size = UDim2.new(0, 25, 0, 25)
                cI.CornerRadius = UDim.new(0, 3)
                cI.Name = "PresetClrCorner"
                cI.Parent = cH
                local function cJ(cK)
                    cH.BackgroundColor3 = Color3.fromHSV(cn, co, cp)
                    cA.BackgroundColor3 = Color3.fromHSV(cn, 1, 1)
                    pcall(bj, cH.BackgroundColor3)
                end
                cn =
                    1 -
                    math.clamp(cG.AbsolutePosition.Y - cD.AbsolutePosition.Y, 0, cD.AbsoluteSize.Y) / cD.AbsoluteSize.Y
                co = math.clamp(cC.AbsolutePosition.X - cA.AbsolutePosition.X, 0, cA.AbsoluteSize.X) / cA.AbsoluteSize.X
                cp =
                    1 -
                    math.clamp(cC.AbsolutePosition.Y - cA.AbsolutePosition.Y, 0, cA.AbsoluteSize.Y) / cA.AbsoluteSize.Y
                cH.BackgroundColor3 = ci
                cA.BackgroundColor3 = ci
                pcall(bj, cH.BackgroundColor3)
                cA.InputBegan:Connect(
                    function(L)
                        if L.UserInputType == Enum.UserInputType.MouseButton1 then
                            if cs then
                                cs:Disconnect()
                            end
                            cs =
                                v.RenderStepped:Connect(
                                function()
                                    local cL =
                                        math.clamp(w.X - cA.AbsolutePosition.X, 0, cA.AbsoluteSize.X) /
                                        cA.AbsoluteSize.X
                                    local cM =
                                        math.clamp(w.Y - cA.AbsolutePosition.Y, 0, cA.AbsoluteSize.Y) /
                                        cA.AbsoluteSize.Y
                                    cC.Position = UDim2.new(cL, 0, cM, 0)
                                    co = cL
                                    cp = 1 - cM
                                    cJ(true)
                                end
                            )
                        end
                    end
                )
                cA.InputEnded:Connect(
                    function(L)
                        if L.UserInputType == Enum.UserInputType.MouseButton1 then
                            if cs then
                                cs:Disconnect()
                            end
                        end
                    end
                )
                cD.InputBegan:Connect(
                    function(L)
                        if L.UserInputType == Enum.UserInputType.MouseButton1 then
                            if ct then
                                ct:Disconnect()
                            end
                            ct =
                                v.RenderStepped:Connect(
                                function()
                                    local cN =
                                        math.clamp(w.Y - cD.AbsolutePosition.Y, 0, cD.AbsoluteSize.Y) /
                                        cD.AbsoluteSize.Y
                                    cG.Position = UDim2.new(0.48, 0, cN, 0)
                                    cn = 1 - cN
                                    cJ(true)
                                end
                            )
                        end
                    end
                )
                cD.InputEnded:Connect(
                    function(L)
                        if L.UserInputType == Enum.UserInputType.MouseButton1 then
                            if ct then
                                ct:Disconnect()
                            end
                        end
                    end
                )
                bg.CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)
            end
            function bi:Textbox(S, cO, cP, bj)
                local cQ = Instance.new("Frame")
                local cR = Instance.new("TextLabel")
                local cS = Instance.new("Frame")
                local cT = Instance.new("UICorner")
                local cU = Instance.new("Frame")
                local cV = Instance.new("UICorner")
                local cW = Instance.new("TextBox")
                cQ.Name = "Textbox"
                cQ.Parent = bg
                cQ.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                cQ.BackgroundTransparency = 1.000
                cQ.Position = UDim2.new(0.0796874985, 0, 0.445175439, 0)
                cQ.Size = UDim2.new(0, 403, 0, 73)
                cR.Name = "TextboxTitle"
                cR.Parent = cQ
                cR.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                cR.BackgroundTransparency = 1.000
                cR.Position = UDim2.new(0, 5, 0, 0)
                cR.Size = UDim2.new(0, 200, 0, 29)
                cR.Font = Enum.Font.Gotham
                cR.Text = S
                cR.TextColor3 = V
                cR.TextSize = 14.000
                cR.TextXAlignment = Enum.TextXAlignment.Left
                cS.Name = "TextboxFrameOutline"
                cS.Parent = cR
                cS.AnchorPoint = Vector2.new(0.5, 0.5)
                cS.BackgroundColor3 = V
                cS.Position = UDim2.new(0.988442957, 0, 1.6197437, 0)
                cS.Size = UDim2.new(0, 396, 0, 36)
                cT.CornerRadius = UDim.new(0, 3)
                cT.Name = "TextboxFrameOutlineCorner"
                cT.Parent = cS
                cU.Name = "TextboxFrame"
                cU.Parent = cR
                cU.BackgroundColor3 = Color3.fromRGB(23, 23, 23)
                cU.ClipsDescendants = true
                cU.Position = UDim2.new(0.00899999978, 0, 1.06638527, 0)
                cU.Selectable = true
                cU.Size = UDim2.new(0, 392, 0, 32)
                cV.CornerRadius = UDim.new(0, 3)
                cV.Name = "TextboxFrameCorner"
                cV.Parent = cU
                cW.Parent = cU
                cW.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                cW.BackgroundTransparency = 1.000
                cW.Position = UDim2.new(0.0178571437, 0, 0, 0)
                cW.Size = UDim2.new(0, 377, 0, 32)
                cW.Font = Enum.Font.Gotham
                cW.PlaceholderColor3 = V
                cW.PlaceholderText = cO
                cW.Text = ""
                cW.TextColor3 = V
                cW.TextSize = 14.000
                cW.TextXAlignment = Enum.TextXAlignment.Left
                cW.Focused:Connect(
                    function()
                        u:Create(
                            cS,
                            TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                            {BackgroundColor3 = Color3.fromRGB(23, 23, 23)}
                        ):Play()
                    end
                )
                cW.FocusLost:Connect(
                    function(cX)
                        u:Create(
                            cS,
                            TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
                            {BackgroundColor3 = V}
                        ):Play()
                        if cX then
                            if #cW.Text > 0 then
                                pcall(bj, cW.Text)
                                if cP then
                                    cW.Text = ""
                                end
                            end
                        end
                    end
                )
                bg.CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)
            end
            function bi:AddImage(cY)
                local cZ =
                    "https://www.roblox.com/asset-thumbnail/image?assetId=" ..
                    game.PlaceId .. "&width=768&height=432&format=png"
                local aH = cZ or cY
                local c_ = Instance.new("Frame")
                local d0 = Instance.new("Frame")
                local d1 = Instance.new("ImageLabel")
                c_.Name = "ImageFrame"
                c_.Parent = bg
                c_.Position = UDim2.new(0.261979163, 0, 0.190789461, 0)
                c_.Size = UDim2.new(0, 401, 0, 105)
                c_.BackgroundTransparency = 1.000
                d1.Name = "gameImageOutline"
                d1.Parent = c_
                d1.Size = UDim2.new(0, 401 * 2 / 4, 0, 125 * 3 / 4)
                d1.Position = UDim2.new(0.125, 0, 0, 0)
                d1.BackgroundTransparency = 1.000
                d1.Image = aH
                bg.CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)
            end
            function bi:AddImage(cY)
                local d2 =
                    "www.roblox.com/avatar-thumbnail/image?userId=" ..
                    game.Players.LocalPlayer.UserId .. "&width=420&height=420&format=png"
                local cZ =
                    "https://www.roblox.com/asset-thumbnail/image?assetId=" ..
                    game.PlaceId .. "&width=768&height=432&format=png"
                local aH = cZ or cY
                local c_ = Instance.new("Frame")
                local d0 = Instance.new("Frame")
                local d1 = Instance.new("ImageLabel")
                c_.Name = "ImageFrame"
                c_.Parent = bg
                c_.Position = UDim2.new(0.261979163, 0, 0.190789461, 0)
                c_.Size = UDim2.new(0, 401, 0, 105)
                c_.BackgroundTransparency = 1.000
                d1.Name = "gameImageOutline"
                d1.Parent = c_
                d1.Size = UDim2.new(0, 401 * 2 / 4, 0, 125 * 3 / 4)
                d1.Position = UDim2.new(0.125, 0, 0, 0)
                d1.BackgroundTransparency = 1.000
                d1.Image = aH
                bg.CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)
            end
            function bi:Label(S)
                local d3 = Instance.new("TextButton")
                local d4 = Instance.new("TextLabel")
                local d5 = {}
                d3.Name = "Label"
                d3.Parent = bg
                d3.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
                d3.BorderSizePixel = 0
                d3.Position = UDim2.new(0.261979163, 0, 0.190789461, 0)
                d3.Size = UDim2.new(0, 401, 0, 30)
                d3.AutoButtonColor = false
                d3.Font = Enum.Font.Gotham
                d3.Text = ""
                d3.TextColor3 = V
                d3.TextSize = 14.000
                d4.Name = "LabelTitle"
                d4.Parent = d3
                d4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                d4.BackgroundTransparency = 1.000
                d4.Position = UDim2.new(0, 5, 0, 0)
                d4.Size = UDim2.new(0, 200, 0, 30)
                d4.Font = Enum.Font.Gotham
                d4.Text = S
                d4.TextColor3 = V
                d4.TextSize = 14.000
                d4.TextXAlignment = Enum.TextXAlignment.Left
                bg.CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)
                function d5:Refresh(bR)
                    d3.Text = bR
                end
                return d5
            end
            function bi:Bind(S, d6, bj)
                local d7 = d6.Name
                local d8 = Instance.new("TextButton")
                local d9 = Instance.new("TextLabel")
                local da = Instance.new("TextLabel")
                d8.Name = "Keybind"
                d8.Parent = bg
                d8.BackgroundColor3 = Color3.fromRGB(23, 23, 23)
                d8.BorderSizePixel = 0
                d8.Position = UDim2.new(0.261979163, 0, 0.190789461, 0)
                d8.Size = UDim2.new(0, 401, 0, 30)
                d8.AutoButtonColor = false
                d8.Font = Enum.Font.Gotham
                d8.Text = ""
                d8.TextColor3 = Color3.fromRGB(255, 255, 255)
                d8.TextSize = 14.000
                d9.Name = "KeybindTitle"
                d9.Parent = d8
                d9.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                d9.BackgroundTransparency = 1.000
                d9.Position = UDim2.new(0, 5, 0, 0)
                d9.Size = UDim2.new(0, 200, 0, 30)
                d9.Font = Enum.Font.Gotham
                d9.Text = S
                d9.TextColor3 = V
                d9.TextSize = 14.000
                d9.TextXAlignment = Enum.TextXAlignment.Left
                da.Name = "KeybindText"
                da.Parent = d8
                da.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
                da.BackgroundTransparency = 1.000
                da.Position = UDim2.new(0, 316, 0, 0)
                da.Size = UDim2.new(0, 85, 0, 30)
                da.Font = Enum.Font.Gotham
                da.Text = d6.Name
                da.TextColor3 = V
                da.TextSize = 14.000
                da.TextXAlignment = Enum.TextXAlignment.Right
                d8.MouseButton1Click:Connect(
                    function()
                        da.Text = "..."
                        local db = game:GetService("UserInputService").InputBegan:wait()
                        if db.KeyCode.Name ~= "Unknown" then
                            da.Text = db.KeyCode.Name
                            d7 = db.KeyCode.Name
                        end
                    end
                )
                game:GetService("UserInputService").InputBegan:connect(
                    function(dc, dd)
                        if not dd then
                            if dc.KeyCode.Name == d7 then
                                pcall(bj)
                            end
                        end
                    end
                )
                bg.CanvasSize = UDim2.new(0, 0, 0, bh.AbsoluteContentSize.Y)
            end
            return bi
        end
        return b6
    end
    return aG
end
local de = s:Window("", _G.Color, _G.Toggle)
local df = de:Server("Bring Hub", "")
local dg = df:Channel("Main")
dg:Toggle(
    "Auto Farm Level",
    false,
    function(bQ)
        getgenv().AutoFarmToggle = bQ
    end
)
dg:Toggle(
    "Fast Attack",
    false,
    function(bQ)
        getgenv().FastAttack = bQ
    end
)
spawn(
    function()
        local dh = require(game.ReplicatedStorage.Util.CameraShaker)
        dh:Stop()
        local di = getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework))[2]
        while wait() do
            if getgenv().FastAttack then
                pcall(
                    function()
                        if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") then
                            di.activeController.timeToNextAttack = 3
                        elseif game.Players.LocalPlayer.Character:FindFirstChild("Electro") then
                            di.activeController.timeToNextAttack = 2
                        else
                            di.activeController.timeToNextAttack = 0
                        end
                        di.activeController.timeToNextAttack = 0
                        di.activeController.attacking = false
                        di.activeController.increment = 3
                        di.activeController.blocking = false
                        di.activeController.timeToNextBlock = 0
                        game.Players.LocalPlayer.Character.Humanoid.Sit = false
                    end
                )
            end
        end
    end
)
if NewWorld then
    dg:Toggle(
        "Auto Third Sea",
        false,
        function(bQ)
            getgenv().AutoThirdSea = bQ
        end
    )
    spawn(
        function()
            pcall(
                function()
                    while wait() do
                        if getgenv().AutoThirdSea then
                            if game:GetService("Players").LocalPlayer.Data.Level.Value >= 1500 and NewWorld then
                                if
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress").KilledIndraBoss ==
                                        false
                                 then
                                    if
                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                            "BartiloQuestProgress",
                                            "Bartilo"
                                        ) == 3
                                     then
                                        if game:GetService("Players").LocalPlayer.Data.SpawnPoint.Value == "Bar" then
                                            if
                                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                                    "TalkTrevor",
                                                    "1"
                                                ) == 0
                                             then
                                                if
                                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                                        "ZQuestProgress",
                                                        "Check"
                                                    ) == 0
                                                 then
                                                    if
                                                        (CFrame.new(-1926.3221435547, 12.819851875305, 1738.3092041016).Position -
                                                            game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <=
                                                            10
                                                     then
                                                        wait(1.1)
                                                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                                            "ZQuestProgress",
                                                            "Begin"
                                                        )
                                                    else
                                                        totarget(
                                                            CFrame.new(
                                                                -1926.3221435547,
                                                                12.819851875305,
                                                                1738.3092041016
                                                            )
                                                        )
                                                    end
                                                    if
                                                        game:GetService("Workspace").Enemies:FindFirstChild(
                                                            "rip_indra [Lv. 1500] [Boss]"
                                                        )
                                                     then
                                                        for l, m in pairs(
                                                            game:GetService("Workspace").Enemies:GetChildren()
                                                        ) do
                                                            if m.Name == "rip_indra [Lv. 1500] [Boss]" then
                                                                repeat
                                                                    game:GetService("RunService").Heartbeat:wait()
                                                                    pcall(
                                                                        function()
                                                                            EquipWeapon(_G.SelectToolWeapon)
                                                                            totarget(
                                                                                m.HumanoidRootPart.CFrame *
                                                                                    CFrame.new(0, 20, 0)
                                                                            )
                                                                            game:GetService "VirtualUser":CaptureController(

                                                                            )
                                                                            game:GetService "VirtualUser":Button1Down(
                                                                                Vector2.new(1280, 672)
                                                                            )
                                                                            m.HumanoidRootPart.Size =
                                                                                Vector3.new(60, 60, 60)
                                                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                                                                "TravelZou"
                                                                            )
                                                                            sethiddenproperty(
                                                                                game.Players.LocalPlayer,
                                                                                "SimulationRadius",
                                                                                math.huge
                                                                            )
                                                                        end
                                                                    )
                                                                until getgenv().AutoThirdSea == false or
                                                                    m.Humanoid.Health <= 0 or
                                                                    not m.Parent
                                                            end
                                                        end
                                                    end
                                                end
                                            end
                                        end
                                    end
                                end
                            end
                        end
                    end
                end
            )
        end
    )
elseif ThreeWorld then
    dg:Toggle(
        "Auto Second Sea",
        false,
        function(bQ)
            getgenv().AutoSecond = bQ
        end
    )
    spawn(
        function()
            while wait(.1) do
                if getgenv().AutoSecond then
                    local j = game.Players.localPlayer.Data.Level.Value
                    if j >= 700 and OldWorld then
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
                        getgenv().SelectWeapon2 = "Key"
                        totarget(CFrame.new(4849.29883, 5.65138149, 719.611877))
                        wait(0.5)
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                            "DressrosaQuestProgress",
                            "Detective"
                        )
                        wait(0.5)
                        if game.Players.LocalPlayer.Backpack:FindFirstChild("Key") then
                            local n = game.Players.LocalPlayer.Backpack:FindFirstChild("Key")
                            wait(.4)
                            game.Players.LocalPlayer.Character.Humanoid:EquipTool(n)
                        end
                        totarget(CFrame.new(1347.7124, 37.3751602, -1325.6488))
                        wait(0.5)
                        game:GetService "VirtualUser":CaptureController()
                        game:GetService "VirtualUser":Button1Down(Vector2.new(1280, 672))
                        if
                            game.Workspace.Enemies:FindFirstChild("Ice Admiral [Lv. 700] [Boss]") and
                                game.Workspace.Map.Ice.Door.CanCollide == false and
                                game.Workspace.Map.Ice.Door.Transparency == 1
                         then
                            EquipWeapon(getgenv().SelectWeapon)
                            if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
                            end
                            for l, m in pairs(game.Workspace.Enemies:GetChildren()) do
                                if
                                    getgenv().AutoSecond and m:IsA("Model") and m:FindFirstChild("Humanoid") and
                                        m:FindFirstChild("HumanoidRootPart") and
                                        m.Humanoid.Health > 0 and
                                        m.Name == "Ice Admiral [Lv. 700] [Boss]"
                                 then
                                    repeat
                                        wait()
                                        pcall(
                                            function()
                                                if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                                        "Buso"
                                                    )
                                                end
                                                m.HumanoidRootPart.Size = Vector3.new(25, 25, 25)
                                                m.HumanoidRootPart.BrickColor = BrickColor.new("White")
                                                m.HumanoidRootPart.CanCollide = false
                                                totarget(m.HumanoidRootPart.CFrame * CFrame.new(0, 25, 0))
                                                game:GetService "VirtualUser":CaptureController()
                                                game:GetService "VirtualUser":Button1Down(Vector2.new(1280, 672))
                                                EquipWeapon(getgenv().SelectWeapon)
                                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                                    "SetSpawnPoint"
                                                )
                                            end
                                        )
                                    until getgenv().AutoSecond == false or not m.Parent or m.Humanoid.Health <= 0
                                end
                            end
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                        else
                            EquipWeapon(getgenv().SelectWeapon2)
                            totarget(CFrame.new(1347.7124, 37.3751602, -1325.6488))
                        end
                    end
                end
            end
        end
    )
end
dg:Toggle(
    "Auto Rengoku",
    false,
    function(bQ)
        getgenv().DoRengoku = bQ
    end
)
dg:Toggle(
    "Auto Bartilo Quest",
    false,
    function(bQ)
        getgenv().DoBartilo = bQ
    end
)
dg:Toggle(
    "Auto Superhuman",
    false,
    function(bQ)
        getgenv().Superhuman = bQ
    end
)
dg:Toggle(
    "Auto Death Step",
    false,
    function(bQ)
        getgenv().DarkLegV2 = bQ
    end
)
dg:Toggle(
    "Auto Buy Legendary Sword",
    false,
    function(bQ)
        getgenv().BuyVipProSword = bQ
    end
)
dg:Toggle(
    "Auto Buy Color Haki",
    false,
    function(bQ)
        getgenv().BuyColorHaki = bQ
    end
)
spawn(
    function()
        while wait(.1) do
            if getgenv().BuyColorHaki then
                local i = {[1] = "ColorsDealer", [2] = "2"}
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
            end
        end
    end
)
spawn(
    function()
        while wait(.1) do
            if getgenv().BuyVipProSword then
                local i = {[1] = "LegendarySwordDealer", [2] = "2"}
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
            end
        end
    end
)
spawn(
    function()
        while wait(.1) do
            if getgenv().DarkLegV2 then
                EquipWeapon("Black Leg")
                if
                    game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 450
                 then
                    local i = {[1] = "BuyDeathStep"}
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                end
                if
                    game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and
                        game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 450
                 then
                    local i = {[1] = "BuyDeathStep"}
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                end
                if
                    game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 449
                 then
                    getgenv().SelectWeapon = "Black Leg"
                end
            end
        end
    end
)
spawn(
    function()
        while wait(.1) do
            if getgenv().Superhuman then
                if
                    game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") or
                        game.Players.LocalPlayer.Character:FindFirstChild("Combat")
                 then
                    local i = {[1] = "BuyBlackLeg"}
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                end
                if
                    game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") or
                        game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") or
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") or
                        game.Players.LocalPlayer.Character:FindFirstChild("Electro") or
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") or
                        game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") or
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") or
                        game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw")
                 then
                    if
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and
                            game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 299
                     then
                        getgenv().SelectWeapon = "Black Leg"
                    end
                    if
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and
                            game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 299
                     then
                        getgenv().SelectWeapon = "Electro"
                    end
                    if
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and
                            game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 299
                     then
                        getgenv().SelectWeapon = "Fishman Karate"
                    end
                    if
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and
                            game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 299
                     then
                        getgenv().SelectWeapon = "Dragon Claw"
                    end
                    if
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and
                            game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 300
                     then
                        local i = {[1] = "BuyElectro"}
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                    end
                    if
                        game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and
                            game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 300
                     then
                        local i = {[1] = "BuyElectro"}
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                    end
                    if
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and
                            game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 300
                     then
                        local i = {[1] = "BuyFishmanKarate"}
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                    end
                    if
                        game.Players.LocalPlayer.Character:FindFirstChild("Electro") and
                            game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 300
                     then
                        local i = {[1] = "BuyFishmanKarate"}
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                    end
                    if
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and
                            game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 300
                     then
                        local i = {[1] = "BlackbeardReward", [2] = "DragonClaw", [3] = "1"}
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                        local i = {[1] = "BlackbeardReward", [2] = "DragonClaw", [3] = "2"}
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                    end
                    if
                        game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and
                            game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 300
                     then
                        local i = {[1] = "BlackbeardReward", [2] = "DragonClaw", [3] = "1"}
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                        local i = {[1] = "BlackbeardReward", [2] = "DragonClaw", [3] = "2"}
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                    end
                    if
                        game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and
                            game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 300
                     then
                        local i = {[1] = "BuySuperhuman"}
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                    end
                    if
                        game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and
                            game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 300
                     then
                        local i = {[1] = "BuySuperhuman"}
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                    end
                end
            end
        end
    end
)
spawn(
    function()
        while wait() do
            if getgenv().DoRengoku and NewWorld then
                if
                    game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or
                        game.Players.LocalPlayer.Character:FindFirstChild("Hidden Key")
                 then
                    EquipWeapon("Hidden Key")
                    totarget(
                        CFrame.new(
                            6571.81885,
                            296.689758,
                            -6966.76514,
                            0.825126112,
                            8.412257e-10,
                            0.564948559,
                            -2.42370835e-08,
                            1,
                            3.39100339e-08,
                            -0.564948559,
                            -4.16727595e-08,
                            0.825126112
                        )
                    )
                elseif
                    game.Workspace.Enemies:FindFirstChild("Snow Lurker [Lv. 1375]") or
                        game.ReplicatedStorage:FindFirstChild("Snow Lurker [Lv. 1375]")
                 then
                    for l, m in pairs(game.Workspace.Enemies:GetChildren()) do
                        if m.Name == "Snow Lurker [Lv. 1375]" then
                            repeat
                                wait()
                                if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
                                end
                                totarget(CFrame.new(5518.00684, 60.5559731, -6828.80518))
                                EquipWeapon(SelectWeapon)
                                totarget(m.HumanoidRootPart.CFrame * CFrame.new(0, 25, 0))
                                m.HumanoidRootPart.Size = Vector3.new(100, 100, 100)
                                game:GetService "VirtualUser":Button1Down(Vector2.new(0, 0.9))
                                game:GetService "VirtualUser":Button1Up(Vector2.new(0, 0.9))
                            until m.Humanoid.Health <= 0 or getgenv().DoRengoku == false or
                                game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or
                                game.Players.LocalPlayer.Character:FindFirstChild("Hidden Key")
                        end
                    end
                elseif
                    game.Workspace.Enemies:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]") or
                        game.ReplicatedStorage:FindFirstChild("Awakened Ice Admiral [Lv. 1400] [Boss]")
                 then
                    for l, m in pairs(game.Workspace.Enemies:GetChildren()) do
                        if m.Name == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
                            repeat
                                wait()
                                if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
                                end
                                EquipWeapon(SelectWeapon)
                                m.HumanoidRootPart.Size = Vector3.new(100, 100, 100)
                                totarget(m.HumanoidRootPart.CFrame * CFrame.new(0, 25, 0))
                                game:GetService "VirtualUser":Button1Down(Vector2.new(0, 0.9))
                                game:GetService "VirtualUser":Button1Up(Vector2.new(0, 0.9))
                            until m.Humanoid.Health <= 0 or getgenv().DoRengoku == false or
                                game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or
                                game.Players.LocalPlayer.Character:FindFirstChild("Hidden Key")
                        end
                    end
                end
            end
        end
    end
)
spawn(
    function()
        while wait() do
            if getgenv().AutoFarmToggle then
                pcall(
                    function()
                        AutoQuest()
                        TP()
                    end
                )
            end
        end
    end
)
spawn(
    function()
        local dh = require(game.ReplicatedStorage.Util.CameraShaker)
        dh:Stop()
        local di = getupvalues(require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework))[2]
        while wait() do
            if getgenv().FastAttack then
                pcall(
                    function()
                        if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") then
                            di.activeController.timeToNextAttack = 3
                        elseif game.Players.LocalPlayer.Character:FindFirstChild("Electro") then
                            di.activeController.timeToNextAttack = 2
                        else
                            di.activeController.timeToNextAttack = 0
                        end
                        di.activeController.timeToNextAttack = 0
                        di.activeController.attacking = false
                        di.activeController.increment = 3
                        di.activeController.blocking = false
                        di.activeController.timeToNextBlock = 0
                        game.Players.LocalPlayer.Character.Humanoid.Sit = false
                    end
                )
            end
        end
    end
)
spawn(
    function()
        local dj = game.Players.LocalPlayer
        local dk = require(dj.PlayerScripts.CombatFramework.Particle)
        local dl = require(game:GetService("ReplicatedStorage").CombatFramework.RigLib)
        if not shared.orl then
            shared.orl = dl.wrapAttackAnimationAsync
        end
        if not shared.cpc then
            shared.cpc = dk.play
        end
        while wait() do
            pcall(
                function()
                    dl.wrapAttackAnimationAsync = function(dm, dn, dp, dq, dr)
                        local ds = dl.getBladeHits(dn, dp, dq)
                        if ds then
                            dk.play = function()
                            end
                            dm:Play(0.1, 0.1, 0.1)
                            dr(ds)
                            dk.play = shared.cpc
                            wait(.1)
                            dm:Stop()
                        end
                    end
                end
            )
        end
    end
)
spawn(
    function()
        while wait() do
            if getgenv().DoBartilo then
                pcall(
                    function()
                        if
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                "BartiloQuestProgress",
                                "Bartilo"
                            ) == 0
                         then
                            if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                    "StartQuest",
                                    "BartiloQuest",
                                    1
                                )
                            end
                            if
                                string.find(
                                    game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,
                                    "Swan Pirates"
                                ) and
                                    string.find(
                                        game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text,
                                        "50"
                                    ) and
                                    game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true
                             then
                                for l, m in pairs(game.Workspace.Enemies:GetChildren()) do
                                    if m.Name == "Swan Pirate [Lv. 775]" then
                                        repeat
                                            wait()
                                            if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                                                local i = {[1] = "Buso"}
                                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                                    unpack(i)
                                                )
                                            end
                                            m.Humanoid.WalkSpeed = 0
                                            m.HumanoidRootPart.CanCollide = false
                                            totarget(m.HumanoidRootPart.CFrame * CFrame.new(0, 25, 0))
                                            game:GetService "VirtualUser":Button1Down(Vector2.new(0, 0.9))
                                            game:GetService "VirtualUser":Button1Up(Vector2.new(0, 0.9))
                                            m.HumanoidRootPart.Size = Vector3.new(100, 100, 100)
                                        until getgenv().DoBartilo == false or m.Humanoid.Health <= 0
                                    end
                                end
                            end
                        elseif
                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                "BartiloQuestProgress",
                                "Bartilo"
                            ) == 1 and game.Players.LocalPlayer.Data.Level.Value >= 850
                         then
                            if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
                                for l, m in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                    if m.Name == "Jeremy [Lv. 850] [Boss]" then
                                        if
                                            m:FindFirstChild("Humanoid") and m:FindFirstChild("HumanoidRootPart") and
                                                m.Humanoid.Health > 0
                                         then
                                            repeat
                                                task.wait()
                                                EquipWeapon(SelectWeapon)
                                                m.Humanoid.WalkSpeed = 0
                                                m.HumanoidRootPart.CanCollide = false
                                                totarget(m.HumanoidRootPart.CFrame * CFrame.new(0, 25, 5))
                                                game:GetService "VirtualUser":Button1Down(Vector2.new(0, 0.9))
                                                game:GetService "VirtualUser":Button1Up(Vector2.new(0, 0.9))
                                                m.HumanoidRootPart.Size = Vector3.new(100, 100, 100)
                                            until m.Humanoid.Health <= 0 or getgenv().DoBartilo == false
                                        end
                                    end
                                end
                            else
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                    "BartiloQuestProgress",
                                    "Bartilo"
                                )
                            end
                        elseif game:GetService("ReplicatedStorage"):FindFirstChild("Jeremy [Lv. 850] [Boss]") then
                            totarget(
                                game:GetService("ReplicatedStorage"):FindFirstChild("Jeremy [Lv. 850] [Boss]").HumanoidRootPart.CFrame *
                                    CFrame.new(0, 25, 5)
                            )
                        elseif
                            game.Players.LocalPlayer.Data.Level.Value >= 850 and
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                                    "BartiloQuestProgress",
                                    "Bartilo"
                                ) == 2
                         then
                            repeat
                                totarget(CFrame.new(-1850.49329, 13.1789551, 1750.89685))
                                wait()
                            until not getgenv().DoBartilo or
                                (game.Players.LocalPlayer.Character.HumanoidRootPart.Position -
                                    Vector3.new(-1850.49329, 13.1789551, 1750.89685)).Magnitude <= 3
                            wait(.3)
                            repeat
                                totarget(CFrame.new(-1858.87305, 19.3777466, 1712.01807))
                                wait()
                            until not getgenv().DoBartilo or
                                (game.Players.LocalPlayer.Character.HumanoidRootPart.Position -
                                    Vector3.new(-1858.87305, 19.3777466, 1712.01807)).Magnitude <= 3
                            wait(.3)
                            repeat
                                totarget(CFrame.new(-1803.94324, 16.5789185, 1750.89685))
                                wait()
                            until not getgenv().DoBartilo or
                                (game.Players.LocalPlayer.Character.HumanoidRootPart.Position -
                                    Vector3.new(-1803.94324, 16.5789185, 1750.89685)).Magnitude <= 3
                            wait(.3)
                            repeat
                                totarget(CFrame.new(-1858.55835, 16.8604317, 1724.79541))
                                wait()
                            until not getgenv().DoBartilo or
                                (game.Players.LocalPlayer.Character.HumanoidRootPart.Position -
                                    Vector3.new(-1858.55835, 16.8604317, 1724.79541)).Magnitude <= 3
                            wait(.3)
                            repeat
                                totarget(CFrame.new(-1869.54224, 15.987854, 1681.00659))
                                wait()
                            until not getgenv().DoBartilo or
                                (game.Players.LocalPlayer.Character.HumanoidRootPart.Position -
                                    Vector3.new(-1869.54224, 15.987854, 1681.00659)).Magnitude <= 3
                            wait(.3)
                            repeat
                                totarget(CFrame.new(-1800.0979, 16.4978027, 1684.52368))
                                wait()
                            until not getgenv().DoBartilo or
                                (game.Players.LocalPlayer.Character.HumanoidRootPart.Position -
                                    Vector3.new(-1800.0979, 16.4978027, 1684.52368)).Magnitude <= 3
                            wait(.3)
                            repeat
                                totarget(CFrame.new(-1819.26343, 14.795166, 1717.90625))
                                wait()
                            until not getgenv().DoBartilo or
                                (game.Players.LocalPlayer.Character.HumanoidRootPart.Position -
                                    Vector3.new(-1819.26343, 14.795166, 1717.90625)).Magnitude <= 3
                            wait(.3)
                            repeat
                                totarget(CFrame.new(-1813.51843, 14.8604736, 1724.79541))
                                wait()
                            until not getgenv().DoBartilo or
                                (game.Players.LocalPlayer.Character.HumanoidRootPart.Position -
                                    Vector3.new(-1813.51843, 14.8604736, 1724.79541)).Magnitude <= 3
                        end
                    end
                )
            end
        end
    end
)
spawn(
    function()
        while wait() do
            if
                getgenv().AutoFarmToggle or getgenv().DoRengoku or getgenv().AutoElite or getgenv().MasteryGun or
                    getgenv().NewWorldStart or
                    getgenv().GoToThirdSea or
                    getgenv().AutoMasteryFruit or
                    getgenv().AutoFarmObservationHaki or
                    getgenv().AutoCakeBoss
             then
                pcall(
                    function()
                        if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Cocaiconcac") then
                            local dt = Instance.new("BodyVelocity")
                            dt.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
                            dt.Name = "Cocaiconcac"
                            dt.MaxForce = Vector3.new(100000, 100000, 100000)
                            dt.Velocity = Vector3.new(0, 0, 0)
                        end
                    end
                )
            else
                if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Cocaiconcac") then
                    game.Players.LocalPlayer.Character.HumanoidRootPart.Cocaiconcac:Destroy()
                end
            end
        end
    end
)
Weapon = {}
for l, m in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
    if m:IsA("Tool") then
        table.insert(Weapon, m.Name)
    end
end
for l, m in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
    if m:IsA("Tool") then
        table.insert(Weapon, m.Name)
    end
end
local du =
    dg:Dropdown(
    "Select Tool",
    Weapon,
    function(n)
        getgenv().SelectWeapon = n
    end
)
dg:Button(
    "Refresh",
    function()
        du:Clear()
        for l, m in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
            if m:IsA("Tool") then
                du:Add(m.Name)
            end
        end
        for l, m in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
            if m:IsA("Tool") then
                du:Add(m.Name)
            end
        end
    end
)
dg:Toggle(
    "Bring",
    false,
    function(bQ)
        getgenv().BringMob = bQ
    end
)
loadstring(game:HttpGet "https://raw.githubusercontent.com/PrimeHubx0/Tool/main/BringMobByNegus.lua")()
function UseCode(dv)
    game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(dv)
end
dg:Button(
    "Redeem All Code",
    function()
        UseCode("Sub2Fer999")
        UseCode("Enyu_is_Pro")
        UseCode("Magicbus")
        UseCode("JCWK")
        UseCode("Starcodeheo")
        UseCode("SUB2GAMERROBOT_EXP1")
        UseCode("StrawHatMaine")
        UseCode("Sub2OfficialNoobie")
        UseCode("FUDD10")
        UseCode("BIGNEWS")
        UseCode("THEGREATACE")
        UseCode("SUB2NOOBMASTER123")
        UseCode("Sub2Daigrock")
        UseCode("Axiore")
        UseCode("TantaiGaming")
        UseCode("STRAWHATMAINE")
    end
)
local dw = {"Sub2UncleKizaru", "SUB2GAMERROBOT_RESET1", "Bluxxy"}
dg:Dropdown(
    "Code Reset Stat",
    dw,
    function(bQ)
        getgenv().Code = bQ
    end
)
dg:Button(
    "Redeem",
    function()
        UseCode(getgenv().Code)
    end
)
dg:Button(
    "Redeem All Reset Stat Code",
    function()
        UseCode("Sub2UncleKizaru")
        UseCode("SUB2GAMERROBOT_RESET1")
        UseCode("Bluxxy")
    end
)
local dx = df:Channel("Auto Stat")
dx:Toggle(
    "Auto Defense",
    false,
    function(bQ)
        getgenv().Health = bQ
    end
)
dx:Toggle(
    "Auto Melee",
    false,
    function(bQ)
        getgenv().Melee = bQ
    end
)
dx:Toggle(
    "Auto Sword",
    false,
    function(bQ)
        getgenv().Sword = bQ
    end
)
dx:Toggle(
    "Auto Gun",
    false,
    function(bQ)
        getgenv().Gun = bQ
    end
)
dx:Toggle(
    "Auto Fruit",
    false,
    function(bQ)
        getgenv().Fruit = bQ
    end
)
getgenv().Point = 1
spawn(
    function()
        while wait() do
            if getgenv().Melee then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Melee", getgenv().Point)
            end
        end
    end
)
spawn(
    function()
        while wait() do
            if getgenv().Health then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Defense", getgenv().Point)
            end
        end
    end
)
spawn(
    function()
        while wait() do
            if getgenv().Sword then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Sword", getgenv().Point)
            end
        end
    end
)
spawn(
    function()
        while wait() do
            if getgenv().Gun then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AddPoint", "Gun", getgenv().Point)
            end
        end
    end
)
spawn(
    function()
        while wait() do
            if getgenv().Fruit then
                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(
                    "AddPoint",
                    "Demon Fruit",
                    getgenv().Point
                )
            end
        end
    end
)
local dy = df:Channel("Bounty")
PlayerList = {}
for l, m in pairs(game.Players:GetChildren()) do
    table.insert(PlayerList, m.Name)
end
local dz =
    dy:Dropdown(
    "Select Players",
    PlayerList,
    function(dA)
        Player = dA
    end
)
dy:Button(
    "Refresh",
    function()
        dz:Clear()
        for l, m in pairs(game.Players:GetChildren()) do
            dz:Add(m.Name)
        end
    end
)
dy:Toggle(
    "Kill Player",
    false,
    function(bQ)
        getgenv().KillPlr = bQ
    end
)
dy:Toggle(
    "Aimbot Gun",
    false,
    function(dB)
        getgenv().Aimbot = dB
    end
)
local dC = game:GetService("Players").LocalPlayer
local dD = dC:GetMouse()
dD.Button1Down:Connect(
    function()
        if getgenv().Aimbot and game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").RemoteFunctionShoot then
            local i = {
                [1] = game:GetService("Players"):FindFirstChild(Player).Character.HumanoidRootPart.Position,
                [2] = game:GetService("Players"):FindFirstChild(Player).Character.HumanoidRootPart
            }
            game.Players.LocalPlayer.Character:FindFirstChildOfClass("Tool").RemoteFunctionShoot:InvokeServer(unpack(i))
        end
    end
)
spawn(
    function()
        local dE = game.Players.LocalPlayer.Character
        local dF = game.Players:FindFirstChild(Player)
    end
)
dy:Toggle(
    "Spectate Player",
    false,
    function(dG)
        repeat
            wait(.1)
            game.Workspace.Camera.CameraSubject = game.Players[getgenv().Player].Character.Humanoid
        until dG == false
        game.Workspace.Camera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
    end
)
spawn(
    function()
        local dE = game.Players.LocalPlayer.Character
        while wait() do
            if getgenv().KillPlr then
                pcall(
                    function()
                        repeat
                            wait(.1)
                            totarget(
                                game.Players:FindFirstChild(getgenv().Player).Character.HumanoidRootPart.CFrame *
                                    CFrame.new(0, 0, 5)
                            )
                            game.Players:FindFirstChild(getgenv().Player).Character.HumanoidRootPart.Size =
                                Vector3.new(50, 50, 50)
                            game:GetService "VirtualUser":Button1Down(Vector2.new(0, 0.9))
                            game:GetService "VirtualUser":Button1Up(Vector2.new(0, 0.9))
                        until getgenv().KillPlr == false
                        game.Players:FindFirstChild(getgenv().Player).Character.HumanoidRootPart.Size =
                            Vector3.new(2, 2, 1)
                    end
                )
            end
        end
    end
)
dy:Toggle(
    "Auto Farm Player",
    false,
    function(bQ)
        getgenv().FarmBounty = bQ
        if game.Players.LocalPlayer.Character.Head:FindFirstChild("OverHead") then
            game.Players.LocalPlayer.Character.Head:FindFirstChild("OverHead"):Destroy()
        end
    end
)
spawn(
    function()
        while wait() do
            if getgenv().FarmBounty then
                eiei = game.Players.LocalPlayer
                for l, m in pairs(game.Players:GetChildren()) do
                    if m.Name ~= eiei.Name then
                        if m.Data.Level.Value >= 1200 then
                            repeat
                                wait()
                                if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
                                    local i = {[1] = "Buso"}
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                                end
                                local i = {[1] = "EnablePvp"}
                                game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(i))
                                NameRandom = m.Name
                                m.Character.HumanoidRootPart.CanCollide = false
                                m.Character.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
                                totarget(m.Character.HumanoidRootPart.CFrame * CFrame.new(0, 0, 3))
                                EquipWeapon(getgenv().SelectWeapon)
                                game:GetService "VirtualUser":CaptureController()
                                game:GetService "VirtualUser":Button1Down(Vector2.new(1280, 672))
                            until getgenv().FarmBounty == false or m.Character.Humanoid.Health == 0
                        end
                    end
                end
            end
        end
    end
)
