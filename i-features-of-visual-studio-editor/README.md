# Visual Studio 에디터의 기능

자주 사용하는 Visual Studio 에디터의 기능을 설명합니다.

# 폰트 설정

코딩을 위해 전용 에디터를 사용하는 것처럼, 코딩을 위한 전용 폰트도 있습니다. 기본적으로 이러한 폰트들은 모든 글자의 너비가 같아야 합니다.

!["Calibri and Consolas"](img/1.png "Calibri and Consolas")

Calibri의 `H`와 `l`의 너비는 다른 반면에, Consolas의 `H`와 `l`은 너비가 같다는 것을 확인할 수 있습니다. 이렇게 모든 글자의 너비가 같은 폰트를 `고정폭 폰트(monospaced font)`라고 합니다. 고정폭 폰트를 사용하면 코드를 더 잘 정리할 수 있고, 코드의 가독성을 높일 수 있습니다.

```cpp
template <typename StringT = std::string>
struct CaseInsensitiveEqual
{
    bool operator()(StringT const& lhs, StringT const& rhs) const
    {
        using namespace std;
        return lhs.size() == rhs.size()
               && equal(lhs.begin(),
                        lhs.end(),
                        rhs.begin(),
                        [](auto l, auto r) {
                            return tolower(l) == tolower(r);
                        });
    }
};

size_t cnt = std::count_if(v.begin(),
                           v.end(),
                           [](auto const& str) {
                               return CaseInsensitiveEqual<
                                   decltype(v)::value_type> {}(str, "hello");
                           });
```

> template \<typename StringT = std::wstring_view\>
> struct CaseInsensitiveEqual
> {
>     bool operator()(StringT const& lhs, StringT const& rhs) const
>     {
>         using namespace std;
>         return lhs.size() == rhs.size()
>                && equal(lhs.begin(),
>                         lhs.end(),
>                         rhs.begin(),
>                         \[\](auto l, auto r) {
>                             return tolower(l) == tolower(r);
>                         });
>     }
> };
>
> size_t cnt = std\:\:count_if(v.begin(),
>                            v.end(),
>                            \[\](auto const& str) {
>                                return CaseInsensitiveEqual\<
>                                    decltype(v)\:\:value_type\> {}(str, "hello");
>                            });

너비가 같은 폰트를 사용하면 각 줄의 들여쓰기를 맞출 수 있는 것에 반해, 너비가 서로 다르면 들여쓰기의 간격을 조절하기 힘들다는 것을 알 수 있습니다.