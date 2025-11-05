# main

```
// dichiarazione della struct
struct master_data{
  bit error;
  bit warning;
  bit on_target_position;
  bit motion_ongoing;
  driver_state_enum master_state;
  working_mode_enum master_working_mode;
  int warning_code;
  float x;
  float y;
  float z;
};

enum master_state_enum{
...,
...,
}

enum master_working_mode_enum{
...,
...,
}

struct axis_data
{
  bit error;
  bit warning;
  bit on_target_position;
  bit motion_ongoing;
  driver_state_enum driver_state;
  working_mode_enum working_mode
  int warning_code;
  float position_deg;
  int position_bit;
  float speed;
  int torque;
};

enum driver_state_enum{
...,
...,
}

enum driver_working_mode_enum{
...,
...,
}

enum targets_type{
target_position_deg,
target_position_bit,
target_speed,
target_torque
}
```

<pre><code>main(){
init();
while(1=1){
<strong>update_exo_data();
</strong>print axis_data[0].speed;
int button_pushed=get_button_pushed();
switch (button_pushed){
    case 0:
            //nessun bottone premuto;
    break;
    case 1:
            //controllo di posizione
            set_axis_working_mode(0,working_mode.position_control);
            set_axis_working_mode(1,working_mode.position_control);
            set_axis_working_mode(2,working_mode.position_control);
            set_axis_working_mode(3,working_mode.position_control);
            set_target(0,target_position_deg, 15.5);
            set_target(1,target_position_deg, 5.5);
            set_target(2,target_position_deg, 90.0);
            set_target(3,target_position_deg,45.0);
break;
}
</code></pre>

