# 690. Employee Importance

Problem: [https://leetcode.com/problems/employee-importance/description/](https://leetcode.com/problems/employee-importance/description/)

作法：

* 先找出對應id的該組 employee info 的 index
* base case：
  * 當對應的index沒有subordinates，return 對應index的importance
* recursive case:
  * 一個一個去跑對應index的subordinates內的index，去跑get\_importance

Language: Ruby

```
=begin
# Employee info
class Employee
    attr_accessor :id, :importance, :subordinates
    def initialize( id, importance, subordinates)
        # It's the unique id of each node.
        # unique id of this employee
        @id = id
        # the importance value of this employee
        @importance = importance
        # the id of direct subordinates
        @subordinates = subordinates
    end
end
=end
# @param {Employee} employees
# @param {Integer} id
# @return {Integer}
def get_importance(employees, id)

    # 想法：
    # 先找出對應id的該組 employee info 的 index
    # base case：
    #     當對應的index沒有subordinates，return 對應index的importance
    # recursive case:
    #     一個一個去跑對應index的subordinates內的index，去跑get_importance

    for i in 0...employees.length
        if employees[i].id == id
            index = i
        end
    end

    if employees[index].subordinates.length == 0
        return employees[index].importance
    end

    ans = employees[index].importance

    for i in 0...employees[index].subordinates.length
       ans = ans + get_importance(employees, employees[index].subordinates[i])
    end

    return ans

end
```



