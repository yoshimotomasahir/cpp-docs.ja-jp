---
title: priority_queue (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::priority_queue
- cliext::priority_queue::assign
- cliext::priority_queue::const_reference
- cliext::priority_queue::container_type
- cliext::priority_queue::difference_type
- cliext::priority_queue::empty
- cliext::priority_queue::generic_container
- cliext::priority_queue::generic_value
- cliext::priority_queue::get_container
- cliext::priority_queue::operator=
- cliext::priority_queue::pop
- cliext::priority_queue::priority_queue
- cliext::priority_queue::push
- cliext::priority_queue::reference
- cliext::priority_queue::size
- cliext::priority_queue::size_type
- cliext::priority_queue::to_array
- cliext::priority_queue::top
- cliext::priority_queue::top_item
- cliext::priority_queue::value_comp
- cliext::priority_queue::value_compare
- cliext::priority_queue::value_type
dev_langs:
- C++
helpviewer_keywords:
- priority_queue class [STL/CLR]
- <queue> header [STL/CLR]
- <cliext/queue> header [STL/CLR]
- assign member [STL/CLR]
- const_reference member [STL/CLR]
- container_type member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- generic_container member [STL/CLR]
- generic_value member [STL/CLR]
- get_container member [STL/CLR]
- operator= member [STL/CLR]
- pop member [STL/CLR]
- priority_queue member [STL/CLR]
- push member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- to_array member [STL/CLR]
- top member [STL/CLR]
- top_item member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: abfe2a740a51ffe8b2735942bc9387f0b13bb0d2
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079532"
---
# <a name="priorityqueue-stlclr"></a>priority_queue (STL/CLR)
このテンプレート クラスは、可変長のアクセスが制限されている要素のシーケンスを順序付けを制御するオブジェクトについて説明します。 コンテナー アダプターを使用する`priority_queue`優先度のキューとしてを基になるコンテナーを管理します。  
  
 下記に、`GValue`と同じ`Value`ref 型を後者には、しない限り、どのケースでは`Value^`します。 同様に、`GContainer`と同じ`Container`ref 型を後者には、しない限り、どのケースでは`Container^`します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename Value,  
    typename Container>  
    ref class priority_queue  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>  
    { ..... };  
```  
  
### <a name="parameters"></a>パラメーター  
 [値]  
 被制御シーケンス内の要素の型。  
  
 コンテナー  
 基になるコンテナーの型。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<cliext/キュー >  
  
 **Namespace:** cliext  

## <a name="declarations"></a>宣言  
  
|型定義|説明|  
|---------------------|-----------------|  
|[priority_queue::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|  
|[priority_queue::container_type (STL/CLR)](#container_type)|基になるコンテナーの型。|  
|[priority_queue::difference_type (STL/CLR)](#difference_type)|2 つの要素間の距離を表す、符号付きの型です。|  
|[priority_queue::generic_container (STL/CLR)](#generic_container)|コンテナー アダプターのジェネリック インターフェイスの型。|  
|[priority_queue::generic_value (STL/CLR)](#generic_value)|コンテナー アダプターのジェネリック インターフェイスの要素の型。|  
|[priority_queue::reference (STL/CLR)](#reference)|要素への参照の型です。|  
|[priority_queue::size_type (STL/CLR)](#size_type)|2 つの要素間の距離を表す、符号付きの型です。|  
|[priority_queue::value_compare (STL/CLR)](#value_compare)|2 つの要素の順序付けのデリゲート。|  
|[priority_queue::value_type (STL/CLR)](#value_type)|要素の型。|  
  
|メンバー関数|説明|  
|---------------------|-----------------|  
|[priority_queue::assign (STL/CLR)](#assign)|すべての要素を置換します。|  
|[priority_queue::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|  
|[priority_queue::get_container (STL/CLR)](#get_container)|基になるコンテナーにアクセスします。|  
|[priority_queue::pop (STL/CLR)](#pop)|Hghest 優先度要素を削除します。|  
|[priority_queue::priority_queue (STL/CLR)](#priority_queue)|コンテナー オブジェクトを構築します。|  
|[priority_queue::push (STL/CLR)](#push)|新しい要素を追加します。|  
|[priority_queue::size (STL/CLR)](#size)|要素の数をカウントします。|  
|[priority_queue::top (STL/CLR)](#top)|最も高い優先順位の要素にアクセスします。|  
|[priority_queue::to_array (STL/CLR)](#to_array)|被制御シーケンスを新しい配列にコピーします。|  
|[priority_queue::value_comp (STL/CLR)](#value_comp)|2 つの要素の順序付けのデリゲートをコピーします。|  
  
|プロパティ|説明|  
|--------------|-----------------|  
|[priority_queue::top_item (STL/CLR)](#top_item)|最も高い優先順位の要素にアクセスします。|  
  
|演算子|説明|  
|--------------|-----------------|  
|[priority_queue::operator= (STL/CLR)](#op_as)|被制御シーケンスを置き換えます。|  
  
## <a name="interfaces"></a>インターフェイス  
  
|Interface|説明|  
|---------------|-----------------|  
|<xref:System.ICloneable>|オブジェクトが重複してください。|  
|IPriorityQueue\<値、コンテナー >|汎用的なコンテナーのアダプターを管理します。|  
  
## <a name="remarks"></a>Remarks  
 オブジェクトは、割り当てし、型の基になるコンテナーを制御するシーケンスの記憶域を解放`Container`、格納する`Value`要素および要求時に増加します。 アクセスとリムーバブル最も高い優先度要素 (最上位の要素) を持つ、ヒープとして順序付けられたシーケンスを保持します。 オブジェクトは、新しい要素をプッシュおよびポップだけでは、最も高い優先度要素優先度のキューの実装へのアクセスを制限します。  
  
 オブジェクトがストアド デリゲート型のオブジェクトを呼び出すことによって、制御するシーケンスを並べ替えます[priority_queue::value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md)です。 Priority_queue; を作成する場合は、ストアド デリゲート オブジェクトを指定することができます。デリゲート オブジェクトを指定しないと、既定値が比較`operator<(value_type, value_type)`です。 このメンバー関数を呼び出すことによってこのストアド オブジェクトにアクセスする[priority_queue::value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)`()`です。  
  
 このようなデリゲート オブジェクト必要があります、厳密弱順序強制型の値で[priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)です。 つまり、任意の 2 つのキーの`X`と`Y`:  
  
 `value_comp()(X, Y)` すべての呼び出しでブール値を同じ結果を返します。  
  
 場合`value_comp()(X, Y)`が true の場合、 `value_comp()(Y, X)` false である必要があります。  
  
 場合`value_comp()(X, Y)`が true の場合、`X`をする前に並べ替えるといいます`Y`です。  
  
 場合`!value_comp()(X, Y) && !value_comp()(Y, X)`が true の場合、`X`と`Y`大小関係が等しいと呼ばれます。  
  
 任意の要素に対して`X`の直前まで`Y`、被制御シーケンスの`key_comp()(Y, X)`は false。 (既定のデリゲート オブジェクトのキーしない値が減少します。)  
  
 最高の優先順位の要素は、その他の要素の前に順序付けされていない先の要素のいずれかでは、です。  
  
 基になるコンテナーでは、要素の順序に並べたヒープとして残される: ため  
  
 コンテナーは、ランダム アクセス反復子をサポートする必要があります。  
  
 同じ順序で要素は、プッシュされたよりも、異なる順序でポップ可能性があります。 (順序付けが安定しない。)  
  
 したがって、候補となる、基になるコンテナーを含める[deque (STL/CLR)](../dotnet/deque-stl-clr.md)と[ベクター (STL/CLR)](../dotnet/vector-stl-clr.md)です。  
  
## <a name="members"></a>メンバー
  
## <a name="assign"></a> priority_queue::assign (STL/CLR)
すべての要素を置換します。  
  
### <a name="syntax"></a>構文  
  
```  
void assign(priority_queue<Value, Container>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コンテナーのアダプターを挿入します。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数を割り当てます`right.get_container()`を基になるコンテナーにします。 使用するキューの内容全体を変更します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_assign.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign a repetition of values   
    Mypriority_queue c2;   
    c2.assign(c1);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
c a b  
```  

## <a name="const_reference"></a> priority_queue::const_reference (STL/CLR)
要素への定数参照の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef value_type% const_reference;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、要素への定数参照を表します。  
  
### <a name="example"></a>例  
  
```  
// cliext_priority_queue_const_reference.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " c b a"   
    for (; !c1.empty(); c1.pop())   
        {   // get a const reference to an element   
        Mypriority_queue::const_reference cref = c1.top();   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  

## <a name="container_type"></a> priority_queue::container_type (STL/CLR)
基になるコンテナーの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Container value_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、テンプレート パラメーター `Container` のシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_container_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Mypriority_queue::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
```  

## <a name="difference_type"></a> priority_queue::difference_type (STL/CLR)
2 つの要素間の距離を符号付きの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef int difference_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、可能性のある負の値の要素の数を表します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_difference_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute negative difference   
    Mypriority_queue::difference_type diff = c1.size();   
    c1.push(L'd');   
    c1.push(L'e');   
    diff -= c1.size();   
    System::Console::WriteLine("pushing 2 = {0}", diff);   
  
// compute positive difference   
    diff = c1.size();   
    c1.pop();   
    c1.pop();   
    c1.pop();   
    diff -= c1.size();   
    System::Console::WriteLine("popping 3 = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
pushing 2 = -2  
popping 3 = 3  
```  

## <a name="empty"></a> priority_queue::empty (STL/CLR)
要素が存在しないかどうかをテストします。  
  
### <a name="syntax"></a>構文  
  
```  
bool empty();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンスが空の場合に true を返します。 等価である[priority_queue::size (STL/CLR)](../dotnet/priority-queue-size-stl-clr.md)`() == 0`です。 Priority_queue が空かどうかをテストに使用するとします。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_empty.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
  
// clear the container and reinspect   
    c1.pop();   
    c1.pop();   
    c1.pop();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    System::Console::WriteLine("empty() = {0}", c1.empty());   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
size() = 3  
empty() = False  
size() = 0  
empty() = True  
```  

## <a name="generic_container"></a> priority_queue::generic_container (STL/CLR)
コンテナーのジェネリック インターフェイスの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Microsoft::VisualC::StlClr::IPriorityQueue<Value>  
    generic_container;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、このテンプレート コンテナーのアダプター クラスのジェネリック インターフェイスを表します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_generic_container.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    Mypriority_queue::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    gc1->push(L'd');   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify original and display generic   
    c1.push(L'e');   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
c a b  
d c b a  
e d b a c  
```  

## <a name="generic_value"></a> priority_queue::generic_value (STL/CLR)
コンテナーのジェネリック インターフェイスを使用するための要素の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef GValue generic_value;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、型のオブジェクトを表します。`GValue`ストアド要素の値をこのテンプレートのコンテナー クラスのジェネリック インターフェイスを使用することについて説明します。 (`GValue`か`value_type`または`value_type^`場合`value_type`ref 型です)。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_generic_value.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get interface to container   
    Mypriority_queue::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display in priority order using generic_value   
    for (; !gc1->empty(); gc1->pop())   
        {   
        Mypriority_queue::generic_value elem = gc1->top();   
  
        System::Console::Write(" {0}", elem);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
c a b  
c b a  
```  

## <a name="get_container"></a> priority_queue::get_container (STL/CLR)
基になるコンテナーにアクセスします。  
  
### <a name="syntax"></a>構文  
  
```  
container_type get_container();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、基になるコンテナーを返します。 使用するコンテナー ラッパーによって指定された制限をバイパスします。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_get_container.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
```  

## <a name="op_as"></a> priority_queue::operator = (STL/CLR)
被制御シーケンスを置き換えます。  
  
### <a name="syntax"></a>構文  
  
```  
priority_queue <Value, Container>% operator=(priority_queue <Value, Container>% right);  
```  
  
#### <a name="parameters"></a>パラメーター  
 右  
 コピーするコンテナーのアダプターです。  
  
### <a name="remarks"></a>Remarks  
 メンバー演算子コピー`right`オブジェクトを返します`*this`です。 これを使用して、被制御シーケンスを `right` の被制御シーケンスのコピーと置き換えます。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_operator_as.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mypriority_queue c2;   
    c2 = c1;   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
c a b  
```  

## <a name="pop"></a> priority_queue::pop (STL/CLR)
Proirity 最上位要素を削除します。  
  
### <a name="syntax"></a>構文  
  
```  
void pop();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、空でない必要があります、被制御シーケンスの最も高い優先度要素を削除します。 使用するバックに 1 つの要素によって、キューを短くします。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_pop.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// pop an element and redisplay   
    c1.pop();   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
b a  
```  

## <a name="priority_queue"></a> priority_queue::priority_queue (STL/CLR)
コンテナー アダプター オブジェクトを構築します。  
  
### <a name="syntax"></a>構文  
  
```  
priority_queue();  
priority_queue(priority_queue<Value, Container> right);  
priority_queue(priority_queue<Value, Container> right);  
explicit priority_queue(value_compare^ pred);  
priority_queue(value_compare^ pred, container_type% cont);  
template<typename InIt>  
    priority_queue(InIt first, InIt last);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred);  
template<typename InIt>  
    priority_queue(InIt first, InIt last,  
        value_compare^ pred, container_type% cont);  
```  
  
#### <a name="parameters"></a>パラメーター  
 続き  
 コピーするコンテナー。  
  
 先頭  
 挿入する範囲の開始しています。  
  
 last  
 挿入する範囲の終了。  
  
 pred  
 被制御シーケンスの述語を順序付けです。  
  
 右  
 挿入するオブジェクトまたは範囲。  
  
### <a name="remarks"></a>Remarks  
 : コンス トラクター  
  
 `priority_queue();`  
  
 既定の順序の述語を空のラップされたコンテナーを作成します。 これを使用するには、既定の順序の述語を持つ、空の初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `priority_queue(priority_queue<Value, Container>% right);`  
  
 ラップされたコンテナーのコピーを作成する`right.get_container()`、順序の指定の述語と`right.value_comp()`です。 キュー オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`right`、同じ順序の指定の述語に置き換えます。  
  
 : コンス トラクター  
  
 `priority_queue(priority_queue<Value, Container>^ right);`  
  
 ラップされたコンテナーのコピーを作成する`right->get_container()`、順序の指定の述語と`right->value_comp()`です。 キュー オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定するために使用`*right`、同じ順序の指定の述語に置き換えます。  
  
 : コンス トラクター  
  
 `explicit priority_queue(value_compare^ pred);`  
  
 順序の指定の述語で、空のラップされたコンテナーを作成`pred`です。 これを使用して、順序指定された述語を持つ、空の初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `priority_queue(value_compare^ pred, container_type cont);`  
  
 順序の指定の述語で、空のラップされたコンテナーを作成`pred`のすべての要素をプッシュ`cont`順序指定された述語で、既存のコンテナーからの初期被制御シーケンスを指定するために使用します。  
  
 : コンス トラクター  
  
 `template<typename InIt> priority_queue(InIt first, InIt last);`  
  
 既定の順序付け述語で、空のラップされたコンテナーを作成し、シーケンスをプッシュ [`first`、 `last`)。 これを使用して、順序指定された述語を持つ、指定した eqeuence からの初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred);`  
  
 順序の指定の述語で、空のラップされたコンテナーを作成`pred`、シーケンスにプッシュし、[`first`、 `last`)。 これを使用して、順序指定された述語を持つ、指定した seqeuence からの初期被制御シーケンスを指定します。  
  
 : コンス トラクター  
  
 `template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred, container_type% cont);`  
  
 順序の指定の述語で、空のラップされたコンテナーを作成`pred`のすべての要素をプッシュ`cont`さらに、シーケンス [`first`、 `last`)。 これを使用して、順序指定された述語を持つ既存のコンテナーと、指定した seqeuence からの初期被制御シーケンスを指定します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_construct.cpp   
// compile with: /clr   
#include <cliext/queue>   
#include <cliext/deque>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
typedef cliext::deque<wchar_t> Mydeque;   
int main()   
    {   
// construct an empty container   
    Mypriority_queue c1;   
    Mypriority_queue::container_type^ wc1 = c1.get_container();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    for each (wchar_t elem in wc1)   
        c2.push(elem);   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule by copying an underlying container   
    Mypriority_queue c2x =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
   for each (wchar_t elem in c2x.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mypriority_queue c3(wc1->begin(), wc1->end());   
    for each (wchar_t elem in c3.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mypriority_queue c4(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>());   
    for each (wchar_t elem in c4.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range, another container, and an ordering rule   
    Mypriority_queue c5(wc1->begin(), wc1->end(),   
        cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c5.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mypriority_queue c6(c3);   
    for each (wchar_t elem in c6.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mypriority_queue c7(%c3);   
    for each (wchar_t elem in c7.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule, by copying an underlying container   
    Mypriority_queue c8 =   
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);   
    for each (wchar_t elem in c8.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
```Output  
size() = 0  
 c a b  
size() = 0  
 a c b  
 a c b  
 c a b  
 a c b  
 a a b c c b  
 c a b  
 c a b  
 a c b  
```  
  
## <a name="push"></a> priority_queue::push (STL/CLR)
新しい要素を追加します。  
  
### <a name="syntax"></a>構文  
  
```  
void push(value_type val);  
```  
  
### <a name="remarks"></a>Remarks  
 メンバー関数は、値を持つ要素を挿入します。`val`に、被制御シーケンス ヒープ作業分野を維持するために、被制御シーケンスの順序を変更するとします。 使用するキューに別の要素を追加します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_push.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
```  
  
## <a name="reference"></a> priority_queue::reference (STL/CLR)
要素への参照の型です。  
  
### <a name="syntax"></a>構文  
  
```  
typedef value_type% reference;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、要素への参照を表します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_reference.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify top of priority_queue and redisplay   
    Mypriority_queue::reference ref = c1.top();   
    ref = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
x a b  
```  

## <a name="size"></a> priority_queue::size (STL/CLR)
要素の数をカウントします。  
  
### <a name="syntax"></a>構文  
  
```  
size_type size();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、被制御シーケンスの長さを返します。 これを使用するには、被制御シーケンス内の現在の要素の数を決定します。 シーケンスが参照してください、0 以外のサイズを持つかどうかは、関心のあるすべて場合[priority_queue::empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)`()`です。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_size.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// pop an item and reinspect   
    c1.pop();   
    System::Console::WriteLine("size() = {0} after popping", c1.size());   
  
// add two elements and reinspect   
    c1.push(L'a');   
    c1.push(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
size() = 3 starting with 3  
size() = 2 after popping  
size() = 4 after adding 2  
```  

## <a name="size_type"></a> priority_queue::size_type (STL/CLR)
2 つの要素の間の距離を符号付きの型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef int size_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、負でない要素の数を表します。  
  
### <a name="example"></a>例  
  
```cpp 
// cliext_priority_queue_size_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mypriority_queue::size_type diff = c1.size();   
    c1.pop();   
    c1.pop();   
    diff -= c1.size();   
    System::Console::WriteLine("size difference = {0}", diff);   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
size difference = 2  
```  
  
## <a name="to_array"></a> priority_queue::to_array (STL/CLR)
被制御シーケンスを新しい配列にコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
cli::array<Value>^ to_array();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数では、被制御シーケンスを格納する配列を返します。 使用する配列形式の被制御シーケンスのコピーを入手します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_to_array.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.push(L'd');   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
d c b a  
c a b  
```  

## <a name="top"></a> priority_queue::top (STL/CLR)
最も高い優先順位の要素にアクセスします。  
  
### <a name="syntax"></a>構文  
  
```  
reference top();  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数では、空でない必要があります、被制御シーケンスのトップ (最高優先度) の要素への参照を返します。 要素にアクセスする、最も高い優先度、存在することがわかっている場合に使用するとします。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_top.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top() = {0}", c1.top());   
  
// alter last item and reinspect   
    c1.top() = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  

## <a name="top_item"></a> priority_queue::top_item (STL/CLR)
最も高い優先順位の要素にアクセスします。  
  
### <a name="syntax"></a>構文  
  
```  
property value_type back_item;  
```  
  
### <a name="remarks"></a>Remarks  
 プロパティでは、空でない必要があります、被制御シーケンスのトップ (最高優先度) 要素にアクセスします。 これを使用するには存在することがわかっている場合に、最も高い優先度要素を読み書きします。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_top_item.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top_item = {0}", c1.top_item);   
  
// alter last item and reinspect   
    c1.top_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 c a b  
top_item = c  
 x a b  
```  

## <a name="value_comp"></a> priority_queue::value_comp (STL/CLR)
2 つの要素の順序付けのデリゲートをコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
value_compare^ value_comp();  
```  
  
### <a name="remarks"></a>Remarks  
 メンバー関数では、被制御シーケンスの並べ替えに使用される順序付けのデリゲートを返します。 使用する 2 つの値を比較します。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_value_comp.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        vcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        vcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        vcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    vcomp = c2.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        vcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        vcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        vcomp(L'b', L'a'));   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
  
compare(L'a', L'a') = False  
compare(L'a', L'b') = False  
compare(L'b', L'a') = True  
```  

## <a name="value_compare"></a> priority_queue::value_compare (STL/CLR)
2 つの値の順序付けのデリゲート。  
  
### <a name="syntax"></a>構文  
  
```  
binary_delegate<value_type, value_type, int> value_compare;  
```  
  
### <a name="remarks"></a>Remarks  
 種類は、最初の引数が 2 つ目の前に順序付けするかどうかを決定するデリゲートのシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_value_compare.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        vcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        vcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        vcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mypriority_queue c2 = cliext::greater<wchar_t>();   
    vcomp = c2.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        vcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        vcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        vcomp(L'b', L'a'));   
    return (0);   
    }  
  
```  
  
```Output  
compare(L'a', L'a') = False  
compare(L'a', L'b') = True  
compare(L'b', L'a') = False  
  
compare(L'a', L'a') = False  
compare(L'a', L'b') = False  
compare(L'b', L'a') = True  
```  

## <a name="value_type"></a> priority_queue::value_type (STL/CLR)
要素の型。  
  
### <a name="syntax"></a>構文  
  
```  
typedef Value value_type;  
```  
  
### <a name="remarks"></a>Remarks  
 この型は、テンプレート パラメーター `Value` のシノニムです。  
  
### <a name="example"></a>例  
  
```cpp  
// cliext_priority_queue_value_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " a b c" using value_type   
    for (; !c1.empty(); c1.pop())   
        {   // store element in value_type object   
        Mypriority_queue::value_type val = c1.top();   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  