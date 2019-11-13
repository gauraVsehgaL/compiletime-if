```markdown
#include <iostream>
#include <string>

std::string GiveMeAStringFromAnything(std::string astring)
{
    return astring;
}

std::string GiveMeAStringFromAnything(int aint)
{
    return std::to_string(aint);
}

template<typename T>
std::string GiveMeAStringFromAnythingLikeABoss(T somet)
{
    if constexpr(std::is_same_v<T, std::string>)
        return somet;
    else if(std::is_same_v<T, int>)
        return std::to_string(somet);
}

int main()
{
    std::string something = "something";
    std::cout<<GiveMeAStringFromAnythingLikeABoss(something);
    std::cout<<GiveMeAStringFromAnythingLikeABoss(42);
}
```
