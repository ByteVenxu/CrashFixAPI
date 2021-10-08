# CrashFixAPI
CrashFix(1.8-1.17.1) API

Event Example:
````java
    @EventHandler(priority = EventPriority.MONITOR)
    private void onCrashEvent(CrashFixCrashEvent crashFixCrashEvent) {
        final Player player = crashFixCrashEvent.getPlayer();

        // Do something...
    }
````

Message Example:
````java
    @EventHandler(priority = EventPriority.MONITOR)
    private void onCrashEvent(CrashFixCrashEvent crashFixCrashEvent) {
        final Player player = crashFixCrashEvent.getPlayer();

        // You can cancel the messages from CrashFix with:
        crashFixCrashEvent.setCancelled(true);

        // For example you can send your own messages:
        Bukkit.getOnlinePlayers().stream().filter(player1 -> player1.hasPermission("your.permission")).forEach(player1 -> {
            final String method = crashFixCrashEvent.getMethod();
            player1.sendMessage(ChatColor.translateAlternateColorCodes('&', "&cThe Player &6" + player.getName() + "&c tried to Crash!"));
            player1.sendMessage(ChatColor.translateAlternateColorCodes('&', "&cThe Method was: &6" + method));
        });
    }
````
