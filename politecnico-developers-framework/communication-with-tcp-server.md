# Communication with TCP server

```
// dichiarazione della struct

const int max_message_length = ...;

enum game_message_id{
empty_0,
autenticazione,
invia_stimolo,
correzione_anti_g,
gioco_start,
gioco_stop,
empty_6,
stato_exo,
invia_log,//per adesso in stand-by
esoscheletro_in_modalita_game,
richiesta_ROM
}

enum game_answer_info_enum{
timestamp,//unsigned_long
current_rep,//unsigned_short
performance,//float
subtask,//short
tempo_attesa,//short
game//byte
//per adesso in stand-by  log_length,//unsigned long
//per adesso in stand-by  log_message//byte[..]
}

int game_answer_info_shared_memory_position[6]={0,4,6,10,12,14};
```

```
byte[max_message_length] = get_game_message(){

}

bool set_game_answer_info(game_answer_info_enum game_answer_info, byte data){
bool info_is_ok = true;
switch(game_answer_info){
    case : game
        save_in_shared_memory(game_answer_info,1,data);
    break;
    default:
        info_is_ok=false;
    break;
return info_is_ok;
}

bool set_game_answer_info(game_answer_info_enum game_answer_info, short data){
bool info_is_ok = true;
switch(game_answer_info){
    case : subtask
    case : tempo_attesa
        save_in_shared_memory(game_answer_info,2,data);
    break;
    default:
        info_is_ok=false;
    break;
return info_is_ok;
}

bool set_game_answer_info(game_answer_info_enum game_answer_info, unsigned_short data){
bool info_is_ok = true;
switch(game_answer_info){
    case : current_rep
        save_in_shared_memory(game_answer_info,2,data);
    break;
    default:
        info_is_ok=false;
    break;
return info_is_ok;
}

bool set_game_answer_info(game_answer_info_enum game_answer_info, float data){
bool info_is_ok = true;
switch(game_answer_info){
    case : performance
        save_in_shared_memory(game_answer_info,4,data);
    break;
    default:
        info_is_ok=false;
    break;
return info_is_ok;
}

bool set_game_answer_info(game_answer_info_enum game_answer_info, unsigned_long data){
bool info_is_ok = true;
switch(game_answer_info){
    case : timestamp
        save_in_shared_memory(game_answer_info,4,data);
    break;
    default:
        info_is_ok=false;
    break;
return info_is_ok;
}

void save_in_shared_memory(game_answer_info_enum game_answer_info,int data_length, byte data[4]){
    for (int i=0;i++;i<data_length){
        int position =  game_answer_info_shared_memory_position[game_answer_info]+i;
        shared_memory[position]=data[i];
    }
}

```

<pre><code><strong>
</strong></code></pre>

