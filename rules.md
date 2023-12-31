扫雷
Input file: standard input
Output file: standard output
Time limit: 1 second
Memory limit: 256 megabytes
扫雷游戏的玩法是在一个9 × 9 (初级)，16 × 16 (中级)，16 × 30 (高级)，或自定义大小的矩阵中随机布
置一定量的地雷 (初级为 10 个，中级为 40 个，高级为 99 个) 。自定义雷区大小不能超过24×30，最小
为9×9，雷数最少10个，最多不能超过雷区的90%。由玩家逐个翻开格子，以找出所有地雷为最终游戏
目标。 如果玩家翻开的格子有地雷，则游戏失败。如果玩家翻开所有没有地雷的格子，则游戏胜利。
游戏的基本操作包括左键单击（Left Click）、右键单击（Right Click）、双击（Chording）三种。其中
左键用于打开安全的格子，推进游戏进度；右键用于标记地雷，以辅助判断，或为接下来的双击做准
备；双击在一个数字周围的地雷标记完时，相当于对数字周围未打开的格子均进行一次左键单击操作。
1. 左键单击：在判断出不是雷的格子上按下左键，可以打开该格子。如果格子上出现数字，则该数字表
示其周围 3 × 3 区域中的地雷数（一般为 8 个格子，对于边块为 5 个格子，对于角块为 3 个格子。所以
扫雷中最大的数字为 8）；如果地雷个数为 0，则可以递归地打开与空相邻的格子；如果不幸触雷，则
游戏结束。
2. 右键单击：在判断为地雷的格子上按下右键，可以标记地雷。重复两次操作可取消标记。重复一次右
键单击可将地雷标记修改为问题标记 "?"。
3. 双击：同时按下左键和右键完成双击。当双击位置周围已标记雷数等于该位置数字时操作有效，相当
于对该数字周围未标记且未打开的格子均进行一次左键单击操作。地雷未标记完全时使用双击无效。若
数字周围有标错的地雷，则游戏结束。
控制台版本的扫雷主要用于OJ平台自动测试提交，用于判断程序的主要逻辑是否正确。为了保证测试的
严谨，初始的地雷所在位置将作为输入提供。
控制台版本需要支持五种操作类型：
1. 左键单击。打开该格子(包括标记为“？”的格子)，如果该格子周围 3 × 3 区域中有雷，则显示雷的个
数；如果地雷个数为 0，则显示为 0 并打开周围 3 × 3 区域中所有未被打开的格子。
2. 右键单击标记地雷。如果该位置为未被打开的格子或问题标记的格子，该位置可以被标记为地雷，
以"!"显示。
3. 右键单击标记问题。如果该位置为未被打开的格子或地雷标记的格子，该位置可以被标记为问题，
以"?"显示。
4. 右键单击取消标记。如果该位置为问题标记或地雷标记的格子，该位置可以被取消标记，恢复为未被
打开的格子。
9.双击。当双击位置周围已标记雷数等于该位置数字时操作有效，相当于对该数字周围未标记为地雷且
未打开的格子均进行一次左键单击操作。地雷未标记完全时使用双击无效。若数字周围有标错的地雷，
则游戏结束。注：如果判断触雷则直接结束，数字周围一个格子都不用打开。
对于每一次操作后，程序需要输出游戏提示、已经进行的操作次数和剩余地雷数量，以及当前棋盘的状
态。
游戏提示共分为三种：
1. 如果玩家未触雷且游戏未胜利，提示"Game in progress"。
2. 如果玩家点开了所有没有雷的格子（不需要完全标记地雷），提示"Game over, you win"。
3. 如果玩家点开有雷的格子，提示"Hit mine, you lose"。
示例可见输入输出样例。
