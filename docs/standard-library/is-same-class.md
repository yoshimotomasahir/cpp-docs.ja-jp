---
title: is_same クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_same
dev_langs:
- C++
helpviewer_keywords:
- is_same class
- is_same
ms.assetid: d9df6c1d-c270-4ec2-802a-af275648dd1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c931e81b27c3a5eb95d546119e0abee118f6e76a
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964978"
---
# <a name="issame-class"></a>is_same クラス

2 つの型が等しいかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty1, class Ty2>
struct is_same;
```

### <a name="parameters"></a>パラメーター

*Ty1*クエリする最初の型。

*Ty2*クエリには、2 番目の型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty1*と*Ty2*同じ型には、それ以外の場合は false を保持します。

## <a name="example"></a>例

```cpp
// std__type_traits__is_same.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct base
    {
    int val;
    };

struct derived
    : public base
    {
    };

int main()
    {
    std::cout << "is_same<base, base> == " << std::boolalpha
        << std::is_same<base, base>::value << std::endl;
    std::cout << "is_same<base, derived> == " << std::boolalpha
        << std::is_same<base, derived>::value << std::endl;
    std::cout << "is_same<derived, base> == " << std::boolalpha
        << std::is_same<derived, base>::value << std::endl;
    std::cout << "is_same<int, int> == " << std::boolalpha
        << std::is_same<int, int>::value << std::endl;
    std::cout << "is_same<int, const int> == " << std::boolalpha
        << std::is_same<int, const int>::value << std::endl;

    return (0);
    }

```

```Output
is_same<base, base> == true
is_same<base, derived> == false
is_same<derived, base> == false
is_same<int, int> == true
is_same<int, const int> == false
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_convertible クラス](../standard-library/is-convertible-class.md)<br/>
[is_base_of クラス](../standard-library/is-base-of-class.md)<br/>
