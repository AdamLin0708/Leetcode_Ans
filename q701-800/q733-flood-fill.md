# 733. Flood Fill

Problem: [https://leetcode.com/problems/flood-fill/description/](https://leetcode.com/problems/flood-fill/description/)

作法：參考討論區

* 使用dfs
* 先紀錄start\_point的color
  * 如果color和new\_color一樣，則直接回傳image
  * 若不一樣，則使用dfs下去跑
* dfs
  * 如果當下的point等於傳進來的color，則將該point color改為new\_color
  * 如果 r &gt;= 1，代表還有左邊的點，則讓最該點左邊處理dfs
  * 如果 c &gt;=1，代表還有上方的點，則讓該點上方處理dfs
  * 如果 r+1 &lt; image.length，代表還有右邊的點，則讓該點右方處理dfs
  * 如果 c+1 &lt; image\[0\].length，代表還有下方的點，則讓該點下方處理dfs

Language: Ruby

```
# @param {Integer[][]} image
# @param {Integer} sr
# @param {Integer} sc
# @param {Integer} new_color
# @return {Integer[][]}
def flood_fill(image, sr, sc, new_color)

    color = image[sr][sc]
    dfs(image, sr, sc, color, new_color) if color != new_color 
    return image

end

def dfs(image, r, c, color, new_color)

    if image[r][c] == color         
        image[r][c] = new_color                
        dfs(image, r-1, c, color, new_color) if r >= 1
        dfs(image, r, c-1, color, new_color) if c >= 1
        dfs(image, r+1, c, color, new_color) if r+1 < image.length
        dfs(image, r, c+1, color, new_color) if c+1 < image[0].length
    end

end
```



