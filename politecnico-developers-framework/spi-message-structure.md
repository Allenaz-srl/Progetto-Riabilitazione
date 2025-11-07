# SPI Message structure



<table><thead><tr><th width="78">byte</th><th width="92">L</th><th>Dato</th><th>Nome</th><th>Note</th></tr></thead><tbody><tr><td>0</td><td>1</td><td>short int</td><td>address</td><td></td></tr><tr><td>1-4</td><td>4</td><td>float</td><td>value</td><td></td></tr><tr><td>5</td><td>1</td><td>int</td><td>Tipo di target 1 e 2</td><td>4 bit per il primo, 4 per il secondo</td></tr><tr><td>6-9</td><td>4</td><td>float</td><td>Target asse 1</td><td></td></tr><tr><td>10-13</td><td>4</td><td>float</td><td>Target asse 2</td><td></td></tr><tr><td>14</td><td>1</td><td>int</td><td>Tipo di target 3 e 4</td><td>4 bit per il primo, 4 per il secondo</td></tr><tr><td>15-18</td><td>4</td><td>float</td><td>Target asse 3</td><td></td></tr><tr><td>19-22</td><td>4</td><td>float</td><td>Target asse 4</td><td></td></tr></tbody></table>
