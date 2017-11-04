# Design Pattern
## Template Method Pattern
#### Concept
- 在父類別定義了一個'Template Method'，用來規範固定行為。將執行過程委託給數個method。讓子類別去各自去implement自己的logic。

```csharp
public interface ILife{
    void Eat();
}

public abstract class DailyLife : ILife{
    public abstract void Breakfast();

    public abstract void Lunch();

    public abstract void Dinner();

    public void Eat(){
        Breakfast();
        Lunch();
        Dinner();
    }
}

public class JeanLife : DailyLife{
    public override void Breakfast(){
        ...
    }

    public override void Lunch(){
        ...
    }

    public override void Dinner(){
        ...
    }

    public void StartNewDay(){
        Eat();
    }
}

```