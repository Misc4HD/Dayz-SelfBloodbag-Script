Dayz-SelfBloodbag
=================

1.Open your dayz_mission.pbo white a pbo manager 

2.Create a new folder called Scripts in your dayz_mission.pbo and add my player_selfBloodbag.sqf to the custom folder you just created!

3.open your fn_selfActions.sqf in YOUR dayz_mission.pbo and add this in
   
    // ---------------------------------------Krixes Self Bloodbag Start------------------------------------
    _mags = magazines player;
 
    // Krixes Self Bloodbag
    if ("ItemBloodbag" in _mags) then {
        hasBagItem = true;
    } else { hasBagItem = false;};
    if((speed player <= 1) && hasBagItem && _canDo) then {
        if (s_player_selfBloodbag < 0) then {
            s_player_selfBloodbag = player addaction[("<t color=""#c70000"">" + ("Self Bloodbag") +"</t>"),"Scripts\player_selfbloodbag.sqf","",5,false,true,"", ""];
        };
    } else {
        player removeAction s_player_selfBloodbag;
        s_player_selfBloodbag = -1;
    };
    // ---------------------------------------Krixes Self Bloodbag End------------------------------------

4.just after this part

      _canDo = (!r_drag_sqf and !r_player_unconscious and !_onLadder);
      
5.You cane find your fn_setfActions.sqf in your dayz_server.pbo
