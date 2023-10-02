# 第一章

## 动态规划

动态规划问题的一般形式是求最值。求解动态规划的核心问题是穷举。

动态规划问题的三要素：最优子结构、状态转移方程、重叠子问题。

1. 只有正确的状态转移方程，才能正确的穷举；
2. 是否具有最优子结构，是否能通过子问题的最值得到原问题的最值；
3. 重叠子问题，使用暴力解法会导致穷举效率低下，需要使用备忘录优化穷举过程。

状态转移方程思考的思路：

明确basecase，明确状态，明确选择，定义dp数组、函数的定义

### 两种框架：

1、自顶向下，递归

```
func main() {
  func dp(状态1, 状态2) result {
    for 选择 = range 所有可能得选择 {
      result = 求最值(result, dp(状态1, 状态2))
    }
    return result
  }
}
```

2、自底向上

```
func main() {
	dp := make() // 1.初始化 basecase
	//2.进行状态转移
	for 状态1 := range 状态1的所有取值 {
		for 状态2 := range 状态2的所有取值 {
			dp[状态1][状态2] = 求最值(选择1, 选择2, ...)
			//3.求result
		}
	}
	//4.result就在dp中，或由dp的值计算得到。
}
```

## 回溯

解决回溯问题就是一个决策树的遍历问题，站在一个回溯树的一个节点上，只需要考虑3个问题：

- 路径：已经做出的选择
- 选择列表：当前可以选择的路径
- 结束条件：到达决策树的底层，无法再做选择的条件

```
func main() {
	res := [][]int{}
	var dfs func(路径, 选择列表)
	dfs = func(路径，选择列表) {
		if 满足条件:
		{
			res = append(res, 路径)
			return
		}
		for 选择 = range 选择列表 {
			做选择
			dfs(路径, 选择列表)
			撤销选择
		}
	}
}
```

递归调用之前 做选择 ，递归调用之后 撤销选择。

## BFS

解决的问题：在图中，找到从起点到终点的最近距离。BFS找到的路径一定是最短的，但是空间复杂度要高很多。

实现：用队列，每次将一个节点周围的所有节点加入队列。

框架：

```
func main() {
	var start Node
	var target Node
	q := []*Node{}
	visited := map[*Node]bool{}
	q = append(q, start)		// 起点加入队列
	visited[start] = true
	step := 0
	for len(q) > 0 {
		sz := len(q)
		// 队列中的所有节点向四周扩散
		for i := 0; i < sz; i++ {
			Node cur := q[0]
			q = q[1:]
			// 判断是否达到终点
			if cur == target {
				return step
			}
			// cur的相邻节点加入队列
			for x := range Node.adj() {
				if (visited[x] == false)
				{
					q = append(q, x)
					visited[x] = true
				}
			}
		}
		// 更新步数
		step++
	}
}
```

## 二叉树

### 二叉树的思维

遍历：问题是否可以通过遍历一遍二叉树获得。用遍历函数+外部变量实现

递归：定义一个递归函数，通过子问题的答案推导出原问题的答案

两种思维的核心：单独抽出二叉树的一个节点，给出需要此节点做的事情，和什么时候（前、中、后序遍历位置）做这些事情。

### 快排和归并排序

快排框架——前序遍历：

```
func sort(nums []int, lo int, hi int) {
	// 前序遍历位置
	// partition，找到切分点p，p的左边比nums[p]小，p的右边比nums[p]大
	p := partition(nums, lo, hi)
	sort(nums, lo, p-1)
	sort(nums, p+1, hi)
}
```

归并排序框架——后续遍历

```
func sort(nums []int, lo int, hi int) {
	m := (lo + hi) / 2
	sort(nums, lo, p-1)
	sort(nums, p+1, hi)
	// 后续遍历位置，合并nums[lo:m]和nums[m+1:hi]
	merge(nums, lo, m, hi)
}
```

### 前、中、后序遍历

前、中、后序是遍历二叉树过程中处理每个节点的三个特殊的时间点：

- 前序：在进入二叉树节点的时候进行；

- 后续：在离开二叉树节点的时候进行；

- 中序：遍历左子树后，将开始遍历右子树时候进行。

对于每个节点都有自己的前、中、后序位置。

![image-20230930144339789](./pic/image-20230930144339789.png)
中序遍历常用于二叉搜索树中。

### 后序遍历的特点

对于那些对前中后序不敏感的代码，可以写在前序遍历中。前序遍历位置只能从函数参数中获取父节点传来的数据，后序遍历位置不仅可以获取参数中的数据，还可以获取到子树通过函数返回值传回来的数据。

比如：节点在第几层，从根节点遍历过来时就能记录下来；节点的子树中有多少节点，就需要遍历完子树后才能清楚。

后序遍历的使用场景：一旦发现了题目和子树有关，大概率要给函数设置合理的定义和返回值，在后序位置写代码了。

## 二分搜索算法

常用场景：寻找一个数，寻找左侧边界，寻找右侧边界。

二分搜索中不要单独写else，要使用else if把所有场景表明清楚。

for中的<和<=的区别：当right是len-1时，表示right是最后一个元素的索引，搜索区间相当于[left, right]，这时要找到中间值需要<=，保证最后一个元素也能被搜索到。当right是len时，right表示最后一个索引的右面的位置，搜索区间相当于[left, right)，找到最后一个值一定是left位置（也是right-1位置），<就可以搜索到最后一个元素的值了。

搜索边界问题，for中如果是<，要使用[left, right)确定搜索区间，循环结束时left==right；for中如果是<=，要使用[left, right]确定搜索区间，循环结束时left==right-1。

### 搜索左侧边界

for中使用<=，nums[mid] == target时，right = mid-1，循环结束后left==right-1，所以左侧位置就是right+1，也就是left。但需要判断左边界是否存在。

```
l, r := 0, len(nums)-1
for l <= r {
    m := (l+r)/2
    if nums[m] < target {
        l = m+1
    } else if nums[m] > target {
        r = m-1
    } else if nums[m] == target {
        r = m-1
    }
}
// 如果存在nums[l]一定==target，l == r+1，所以l>=0。当所有元素都<target时，r为len-1，这时l就会==len。综上，l的范围是[0, len]
if l == len(nums) || nums[l] != target {
    return -1
}
return l
```

### 搜索右侧边界

for中使用<=，nums[mid] == target时，left = mid+1，循环结束后left==right-1，所以右侧位置就是left-1，也就是right。但需要判断右边界是否存在。

```
l, r := 0, len(nums)-1
for l <= r {
    m := (l+r)/2
    if nums[m] < target {
        l = m+1
    } else if nums[m] > target {
        r = m - 1
    } else if nums[m] == target {
        l = m+1
    }
}
// r的范围是[-1, len-1]，当所有元素都>target时右边界就是-1。
if r < 0 || nums[r] != target {
    return -1
}
return r
```

## 滑动窗口

滑动窗口属于双指针技巧。常用于处理字符串相关问题。

思路：维护一个窗口不断滑动，然后更新答案。

```
left, right := 0, 0
for r < len {
	// 右侧元素添加到窗口中，增加窗口
	window.add(s[right])
	right++
	// 满足窗口缩短条件后，窗口减小
	for left < right && 满足窗口缩短条件 {
		window.remove(s[left])
		left++
	}
}
```

框架：

```
func slidingWindow(s string) {
	window := map[byte]int{} // 窗口可以以多种形式存在
	left, right := 0, 0
  for left < right && right < len {
    // 右侧元素添加到窗口中，增加窗口
    c := s[right]
    window.add(c)
    right++
    // 更新窗口内的数据(扩大窗口的更新操作)
    ...
    /* debug位置 */
    fmt.Println("window:", left, right)
    // 判断左侧窗口是否要缩小
    for left < right && 满足窗口缩短条件 {
      window.remove(s[left])
      left++
      // 更新窗口内数据(缩小窗口的更新操作)
      ...
    }
  }
}
```

第二章

双指针：

快慢指针

滑动窗口、链表、

左右指针

二分、两数之和、翻转数组、回文串



前缀和：

不修改原数组的情况下，频繁求区间内元素累加和。



差分数组

频繁对原始元素的某个区间的元素进行加减，频繁操作后，输出结果数组。

先构造出差分数组diff，diff[i] = nums[i]-nums[i-1]。

[i, j]的元素+1：diff[i] = diff[i]+1, diff[j+1] = diff[j+1] - 1

通过diff构造出原数组：nums[i] = nums[i-1] + diff[i]



LRU



LFU



O(1)的复杂度删除/查找数组中的元素

- 查找：数据的底层存储一定使用紧凑的数组
- 添加：元素添加到数组最后
- 删除：要删除的元素交换到数组最后的位置，为了找到每个元素的索引，需要使用map保存每个元素的索引。



单调栈



单调队列
