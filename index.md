```
#include <iostream>
#include <string>

template<size_t n>
int fact()
{
    return fact<n-1>() + fact<n-2>();
}

template<>
int fact<1>()
{
    return 1;
}

template<>
int fact<2>()
{
    return 1;
}

template<size_t n>
int FactLikeABoss()
{
    if constexpr(n==1)
        return 1;
    else if constexpr(n==2)
        return 1;
    else
       return FactLikeABoss<n-1>() + FactLikeABoss<n-2>();
}

int main()
{
    std::cout<<FactLikeABoss<1>()<<'\n';
    std::cout<<FactLikeABoss<2>()<<'\n';
    std::cout<<FactLikeABoss<3>()<<'\n';
    std::cout<<FactLikeABoss<4>()<<'\n';
    std::cout<<FactLikeABoss<5>()<<'\n';
    std::cout<<FactLikeABoss<6>()<<'\n';
}
```
