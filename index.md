```
#include <iostream>
#include <string>

template<size_t n>
int fibonacci()
{
    return fibonacci<n-1>() + fibonacci<n-2>();
}

template<>
int fibonacci<1>()
{
    return 1;
}

template<>
int fibonacci<2>()
{
    return 1;
}

template<size_t n>
int fibonacciLikeABoss()
{
    if constexpr(n==1)
        return 1;
    else if constexpr(n==2)
        return 1;
    else
       return fibonacciLikeABoss<n-1>() + fibonacciLikeABoss<n-2>();
}

int main()
{
    std::cout<<fibonacciLikeABoss<1>()<<'\n';
    std::cout<<fibonacciLikeABoss<2>()<<'\n';
    std::cout<<fibonacciLikeABoss<3>()<<'\n';
    std::cout<<fibonacciLikeABoss<4>()<<'\n';
    std::cout<<fibonacciLikeABoss<5>()<<'\n';
    std::cout<<fibonacciLikeABoss<6>()<<'\n';
}
```
