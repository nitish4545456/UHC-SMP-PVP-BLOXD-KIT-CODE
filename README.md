const allowedPlayers = ["HASSANxSIGMA_","ShortStack_YT", "X_LITTLE_MONSTER_X"];
let commandsEnabled = true;

onPlayerChat = (playerId, chatMessage) => {
  if (!playerId) return false;
  
  if (chatMessage.substring(0, 1) !== "!") return;
  
  const name = api.getEntityName(playerId);
  if (!name) return false;
  
  const cmd = chatMessage.substring(1).trim().toLowerCase();
  
  if (!commandsEnabled && !allowedPlayers.includes(name) && cmd !== "allow") {
    api.sendMessage(playerId, "Commands are disabled.");
    return false;
  }
  
  if (cmd === "allow" && allowedPlayers.includes(name)) {
    commandsEnabled = true;
    api.broadcastMessage("Commands enabled.");
    return false;
  }
  
  if (cmd === "disallow" && allowedPlayers.includes(name)) {
    commandsEnabled = false;
    api.broadcastMessage("Commands disabled.");
    return false;
  }
  
  if (cmd === "clear") {
    api.clearInventory(playerId);
    api.sendMessage(playerId, "Inventory cleared.");
    return false;
  }
  
 // 🔥 SMP KIT (your FULL enchanted kit)
  if (cmd === "smp") {
    api.clearInventory(playerId);
    
    // Enchanted Weapons
    api.giveItem(playerId, "Diamond Sword", 1, {
      customAttributes: {enchantments: {"Damage": 3,"Attack Speed": 2}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Sword",
      customDescription: ""
    });
    api.giveItem(playerId, "Diamond Pickaxe", 1, {
      customAttributes: {enchantments: {"Momentum": 2,"Break Speed": 3}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Pickaxe",
      customDescription: ""
    });
    api.giveItem(playerId, "Diamond Bow", 1, {
      customAttributes: {enchantments: {"Attack Speed": 2,"Quick Charge": 3}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Bow",
      customDescription: ""
    });
    api.giveItem(playerId, "Diamond Mace", 1, {
      customAttributes: {enchantments: {"Damage": 3,"Attack Speed": 2}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Mace",
      customDescription: ""
    });
    api.giveItem(playerId, "Diamond Spear", 1, {
      customAttributes: {enchantments: {"Damage": 3,"Attack Speed": 2}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Spear",
      customDescription: ""
    });
    
    // Enchanted Armor
    api.setItemSlot(playerId, 46, "Diamond Helmet", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 47, "Diamond Chestplate", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 48, "Diamond Gauntlets", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 49, "Diamond Leggings", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 50, "Diamond Boots", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    
    // SMP Items
    api.giveItem(playerId, "Diamond Hang Glider", 1);
    api.giveItem(playerId, "Iceball", 999);
    api.giveItem(playerId, "Baked Potato", 999);
    api.giveItem(playerId, "Net", 999);
    api.giveItem(playerId, "Diamond Spikes", 999);
    api.giveItem(playerId, "Mango", 999);
    api.giveItem(playerId, "Compressed Messy Stone", 999);
    api.giveItem(playerId, "Arrow of Poison", 999);
    api.giveItem(playerId, "Rainbow Firecracker", 999);
    api.giveItem(playerId, "Pear", 100);
    
    api.sendMessage(playerId, "🛠️ SMP KIT RECEIVED!", { color: "green" });
    return false;
  }
  
  // 🔥 UHC KIT (YOUR EXACT WORKING KIT)
  if (cmd === "uhc") {
    api.clearInventory(playerId);
    
    // YOUR EXACT UHC KIT ↓
    api.setItemSlot(playerId, 46, "Diamond Helmet", 1, {
      customAttributes: {
        enchantments: { Protection: 3, "Health Regen": 2, Damage: 10000000 },
        enchantmentTier: "Tier 5",
      },
    });
    api.setItemSlot(playerId, 47, "Diamond Chestplate", 1, {
      customAttributes: {
        enchantments: { Protection: 3, "Health Regen": 2 },
        enchantmentTier: "Tier 5",
      },
    });
    api.setItemSlot(playerId, 48, "Diamond Gauntlets", 1, {
      customAttributes: {
        enchantments: { Protection: 3, "Health Regen": 2 },
        enchantmentTier: "Tier 5",
      },
    });
    api.setItemSlot(playerId, 49, "Diamond Leggings", 1, {
      customAttributes: {
        enchantments: { Protection: 3, "Health Regen": 2 },
        enchantmentTier: "Tier 5",
      },
    });
    api.setItemSlot(playerId, 50, "Diamond Boots", 1, {
      customAttributes: {
        enchantments: { Protection: 3, "Health Regen": 2 },
        enchantmentTier: "Tier 5",
      },
    });
    api.giveItem(playerId, "Diamond Sword", 1, {
      customAttributes: {
        enchantments: { Damage: 2, "Attack Speed": 3 },
        enchantmentTier: "Tier 5",
      },
    });
    api.giveItem(playerId, "Diamond Pickaxe", 1, {
      customAttributes: {
        enchantments: { "Break Speed": 3, Momentum: 2 },
        enchantmentTier: "Tier 5",
      },
    });
    api.giveItem(playerId, "Diamond Axe", 1, {
      customAttributes: {
        enchantments: { "Break Speed": 3, Momentum: 2 },
        enchantmentTier: "Tier 5",
      },
    });
    api.giveItem(playerId, "Net", 600);
    api.giveItem(playerId, "Diamond Spikes", 400);
    api.giveItem(playerId, "Corn", 300);
    api.giveItem(playerId, "Pear", 100);
    api.giveItem(playerId, "Splash Instant Healing Potion II", 32);
    api.giveItem(playerId, "Splash Weakness Potion II", 7);
    // ↑ YOUR EXACT UHC KIT
    
    api.sendMessage(playerId, "⚔️ UHC KIT RECEIVED!", { color: "red" });
    return false;
  }
  
  // 🔥 PVP KIT (Armor + Sword + Pickaxe)
  if (cmd === "pvp") {
    api.clearInventory(playerId);
    
    api.setItemSlot(playerId, 46, "Diamond Helmet", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 47, "Diamond Chestplate", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 48, "Diamond Gauntlets", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 49, "Diamond Leggings", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    api.setItemSlot(playerId, 50, "Diamond Boots", 1, {
      customAttributes: {enchantments: {Protection: 3, "Health Regen": 2}, enchantmentTier: "Tier 5"}
    });
    
    api.giveItem(playerId, "Diamond Sword", 1, {
      customAttributes: {enchantments: {"Damage": 3,"Attack Speed": 2}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Sword", customDescription: ""
    });
    api.giveItem(playerId, "Diamond Pickaxe", 1, {
      customAttributes: {enchantments: {"Momentum": 2,"Break Speed": 3}, enchantmentTier: "Tier 5"},
      customDisplayName: "Enchanted Pickaxe", customDescription: ""
    });
    
    api.sendMessage(playerId, "💥 PVP KIT RECEIVED!", { color: "purple" });
    return false;
  }
   // 🔥 HELP COMMAND (NEW!)
  if (cmd === "help") {
    api.sendMessage(playerId, [
      { str: "🎮 §lKIT COMMANDS §r\n\n", style: { color: "aqua" } },
      { str: "!smp - for Full Survival Kit (weapons + armor + items)\n", style: { color: "Yellow" } },
      { str: "!uhc - UHC Kit (helmet + potions + food)\n", style: { color: "Red" } },
      { str: "!pvp - PvP Kit (armor + sword + pickaxe)\n", style: { color: "white" } },
      { str: "!clear - Clear inventory\n\n", style: { color: "Orange" } },
     ]);
    return false;
  }

  
  return false;
};
