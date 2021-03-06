---
title: 数値 (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- <cliext/numeric>
- cliext::accumulate
- cliext::adjacent_difference
- cliext::inner_product
- cliext::partial_sum
dev_langs:
- C++
helpviewer_keywords:
- numeric functions [STL/CLR]
- <cliext/numeric> header [STL/CLR]
- <numeric> header [STL/CLR]
- accumulate function [STL/CLR]
- adjacent_difference function [STL/CLR]
- inner_product function [STL/CLR]
- partial_sum function [STL/CLR]
ms.assetid: 1dc4d9a3-e734-459c-9678-5d9be0ef4c79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f8d470928cb4cbc1625ad439efe75b97f2bb1bd7
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079042"
---
# <a name="numeric-stlclr"></a>数値 (STL/CLR)
数値処理のために用意されているアルゴリズムを実行するコンテナーのテンプレート関数を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <cliext/numeric>  
```  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/numeric >  
  
 **Namespace:** cliext  
  
## <a name="declarations"></a>宣言  
  
|関数|説明|  
|--------------|-----------------|  
|[accumulate (STL/CLR)](#accumulate)|連続する部分和を計算することで、いくつかの初期値を含め、指定された範囲のすべての要素の合計を計算します。または、指定された二項演算を使用して取得した、合計以外の連続する部分的な結果を計算します。|  
|[adjacent_difference (STL/CLR)](#adjacent_difference)|入力範囲内の各要素とその先行要素との連続する差分を計算し、結果をターゲット範囲に出力するか、または差分演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|  
|[inner_product (STL/CLR)](#inner_product)|2 つの範囲の要素ごとの積の合計を計算し、それを指定された初期値に加算するか、または和や積の二項演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|  
|[partial_sum (STL/CLR)](#partial_sum)|一連の最初の要素から入力範囲内の合計を計算、`i`番目の要素でこのような各合計の結果を格納および`i`番目の要素をターゲット範囲の汎用化されたプロシージャの結果を計算または場所合計演算指定した別の二項演算に置き換えられます。|  
 
## <a name="members"></a>メンバー

## <a name="accumulate"></a> accumulate (STL/CLR)
連続する部分和を計算することで、いくつかの初期値を含め、指定された範囲のすべての要素の合計を計算します。または、指定された二項演算を使用して取得した、合計以外の連続する部分的な結果を計算します。  
  
### <a name="syntax"></a>構文  
  
```  
template<class _InIt, class _Ty> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);  
template<class _InIt, class _Ty, class _Fn2> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);  
```  
  
### <a name="remarks"></a>Remarks  
 この関数の動作は、C++ 標準ライブラリの数値関数と同じ`accumulate`です。 詳細については、次を参照してください。[蓄積](../standard-library/numeric-functions.md#accumulate)です。  

## <a name="adjacent_difference"></a> adjacent_difference (STL/CLR)
入力範囲内の各要素とその先行要素との連続する差分を計算し、結果をターゲット範囲に出力するか、または差分演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。  
  
### <a name="syntax"></a>構文  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
### <a name="remarks"></a>Remarks  
 この関数の動作は、C++ 標準ライブラリの数値関数と同じ`adjacent_difference`です。 詳細については、次を参照してください。 [adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)です。  

## <a name="inner_product"></a> inner_product (STL/CLR)
2 つの範囲の要素ごとの積の合計を計算し、それを指定された初期値に加算するか、または和や積の二項演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。  
  
###<a name="syntax"></a>構文  
  
```  
template<class _InIt1, class _InIt2, class _Ty> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val);  
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,  
       class _Fn22> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);  
```  
  
### <a name="remarks"></a>Remarks  
 この関数の動作は、C++ 標準ライブラリの数値関数と同じ`inner_product`です。 詳細については、次を参照してください。 [inner_product](../standard-library/numeric-functions.md#inner_product)です。

## <a name="partial_sum"></a> partial_sum (STL/CLR)
一連の最初の要素から入力範囲内の合計を計算、`i`番目の要素でこのような各合計の結果を格納および`i`番目の要素をターゲット範囲の汎用化されたプロシージャの結果を計算または場所合計演算指定した別の二項演算に置き換えられます。  
  
### <a name="syntax"></a>構文  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
### <a name="remarks"></a>Remarks  
 この関数の動作は、C++ 標準ライブラリの数値関数と同じ`partial_sum`です。 詳細については、次を参照してください。 [partial_sum](../standard-library/numeric-functions.md#partial_sum)です。  
    