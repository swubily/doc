1. 
2. 多一个表 通过继承的方式创建多个实体

```
@DiscriminatorValue( value="TS" ) 关联字段
@Entity
@DiscriminatorValue( value = "NS" )
public class NonTeachingStaff extends Staff
```