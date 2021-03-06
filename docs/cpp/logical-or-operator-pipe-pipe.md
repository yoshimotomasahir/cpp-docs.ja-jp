---
title: '論理 OR 演算子: | ||Microsoft Docs'
ms.custom: ''
ms.date: 06/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '||'
dev_langs:
- C++
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ce7b3085a66cf731da4373c534a95d09225d8ae
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943229"
---
# <a name="logical-or-operator-"></a>論理 OR 演算子: | |

## <a name="syntax"></a>構文

> *論理-または-式* **||** *論理-と-式*

## <a name="remarks"></a>Remarks

論理 OR 演算子 (**||**) 場合、いずれかまたは両方のオペランドが TRUE であり、それ以外の場合は FALSE を返します、ブール値 TRUE を返します。 オペランドは型に暗黙的に変換**bool**前に、evaluation、および結果の種類では**bool**します。 論理 OR の結合規則は左から右です。

論理 OR 演算子のオペランドが同じ型である必要はありませんが、整数型またはポインター型である必要があります。 オペランドは一般に関係式または等価式です。

最初のオペランドが完全に評価され、すべての副作用が完了した後で、論理 OR 式の評価が続行されます。

2 番目のオペランドは、最初のオペランドが false (0) と評価された場合にのみ、評価されます。 これにより、論理 OR 式が true の場合に 2 番目のオペランドの無駄な評価が行われないようになっています。

```cpp
printf( "%d" , (x == w || x == y || x == z) );
```

上の例では、`x` が `w`、`y`、または `z` と等しい場合、`printf` 関数の 2 番目の引数が true に評価され、値 1 が出力されます。 それ以外の場合は、false と評価され、値 0 が出力されます。 条件の 1 つが true と評価されると、直ちに評価が終了します。

## <a name="operator-keyword-for-124124"></a>演算子キーワード&#124;&#124;

**または**演算子と等価のテキストは、  **||** します。 アクセスする 2 つの方法がある、**または**演算子をプログラムで: ヘッダー ファイルをインクルード\<iso646.h > を使用してコンパイル、 [/Za](../build/reference/za-ze-disable-language-extensions.md) (言語拡張を無効にする) コンパイラ オプション。

## <a name="example"></a>例

```cpp
// expre_Logical_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate logical OR
#include <iostream>
using namespace std;
int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b || b > c yields "
         << (a < b || b > c) << endl
         << "The false expression "
         << "a > b || b > c yields "
         << (a > b || b > c) << endl;
}
```

## <a name="see-also"></a>関連項目

- [C++ の組み込み演算子の優先順位と結合規則](cpp-built-in-operators-precedence-and-associativity.md)
- [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
- [C 論理演算子](../c-language/c-logical-operators.md)