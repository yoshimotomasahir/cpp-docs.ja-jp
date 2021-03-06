---
title: (C++ コンポーネント拡張) の型の特徴のコンパイラ サポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- __is_simple_value_class
- __has_trivial_destructor
- __has_assign
- __is_union
- __is_class
- __is_abstract
- __has_trivial_assign
- __has_virtual_destructor
- __is_ref_array
- __is_base_of
- __has_copy
- __is_polymorphic
- __has_nothrow_constructor
- __is_ref_class
- __is_delegate
- __is_convertible_to
- __is_value_class
- __is_interface_class
- __has_nothrow_copy
- __is_sealed
- __has_trivial_constructor
- __has_trivial_copy
- __is_enum
- __has_nothrow_assign
- __has_finalizer
- __is_empty
- __is_pod
- __has_user_destructor
dev_langs:
- C++
helpviewer_keywords:
- __is_class keyword [C++]
- __is_pod keyword [C++]
- __is_delegate keyword [C++]
- __is_value_class keyword [C++]
- __has_copy keyword [C++]
- __has_nothrow_copy keyword [C++]
- __is_interface_class keyword [C++]
- __is_sealed keyword [C++]
- __is_convertible_to keyword [C++]
- __is_ref_class keyword [C++]
- __has_trivial_copy keyword [C++]
- __has_user_destructor keyword [C++]
- __is_abstract keyword [C++]
- __is_empty keyword [C++]
- __has_trivial_assign keyword [C++]
- __has_nothrow_constructor keyword [C++]
- __is_ref_array keyword [C++]
- __is_base_of keyword [C++]
- __has_nothrow_assign keyword [C++]
- __has_virtual_destructor keyword [C++]
- __has_finalizer keyword [C++]
- __is_union keyword [C++]
- __has_assign keyword [C++]
- __has_trivial_destructor keyword [C++]
- __is_polymorphic keyword [C++]
- __is_enum keyword [C++]
- __is_simple_value_class keyword [C++]
- __has_trivial_constructor keyword [C++]
ms.assetid: cd440630-0394-48c0-a16b-1580b6ef5844
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c68e354e70f3976bffba12020ff1175142715fbc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862417"
---
# <a name="compiler-support-for-type-traits-c-component-extensions"></a>型の特徴のコンパイラ サポート (C++ コンポーネント拡張)
コンパイラ サポート*特徴 (traits) を入力*コンパイル時に、型のさまざまな特性をかを示すです。  
  
## <a name="all-runtimes"></a>すべてのランタイム  
 **解説**  
  
 型の特徴は、ライブラリを記述するプログラマにとって特に便利です。  
  
 次の一覧には、コンパイラによってサポートされている型の特徴が含まれています。 型の特徴の名前で指定された条件を満たさない場合、すべての型の特徴により `false` が返されます。  
  
 (次の一覧でのコード例はで作成されたのみ C + + CLI です。 ただし、対応する型の特徴は、特に明記されていない限り、[!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] でもサポートされます。 「プラットフォーム型」とは Windows ランタイム型または共通言語ランタイム型のいずれかです。)  
  
-   `__has_assign(` `type` `)`  
  
     プラットフォーム型またはネイティブ型にコピー代入演算子がある場合は true を返します。  
  
    ```  
  
    ref struct R {  
    void operator=(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_assign(R));  
    }  
  
    ```  
  
-   `__has_copy(` `type` `)`  
  
     プラットフォーム型またはネイティブ型にコンストラクターがある場合は true を返します。  
  
    ```  
  
    ref struct R {  
    R(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_copy(R));  
    }  
  
    ```  
  
-   `__has_finalizer(` `type` `)`  
  
     ([!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] ではサポートされていません。)CLR 型にファイナライザーがある場合は true を返します。 参照してください[する方法のデストラクターおよびファイナライザー: を定義およびクラスと構造体を使用 (C + + CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)詳細についてはします。  
  
    ```  
  
    using namespace System;  
    ref struct R {  
    ~R() {}  
    protected:  
    !R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_finalizer(R));  
    }  
  
    ```  
  
-   `__has_nothrow_assign(` `type` `)`  
  
     コピー代入演算子に空の例外の指定がある場合は true を返します。  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    void operator=(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_nothrow_constructor(` `type` `)`  
  
     既定のコンストラクターに空の例外の指定がある場合は true を返します。  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    S() throw() {}  
    };  
  
    int main() {  
    __has_nothrow_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_nothrow_copy(` `type` `)`  
  
     コピー コンストラクターに空の例外の指定がある場合は true を返します。  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    S(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_assign(` `type` `)`  
  
     型に単純なコンパイラにより生成された代入演算子がある場合は true を返します。  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_constructor(` `type` `)`  
  
     型に単純なコンパイラにより生成されたコンストラクターがある場合は true を返します。  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_copy(` `type` `)`  
  
     型に単純なコンパイラにより生成されたコピー コンストラクターがある場合は true を返します。  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_destructor(` `type` `)`  
  
     型に単純なコンパイラにより生成されたデストラクターがある場合は true を返します。  
  
    ```  
  
    // has_trivial_destructor.cpp  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_user_destructor(` `type` `)`  
  
     プラットフォーム型またはネイティブ型にユーザーが宣言したデストラクターがある場合は true を返します。  
  
    ```  
  
    // has_user_destructor.cpp  
  
    using namespace System;  
    ref class R {  
    ~R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_user_destructor(R));  
    }  
  
    ```  
  
-   `__has_virtual_destructor(` `type` `)`  
  
     型に仮想デストラクターがある場合は true を返します。  
  
     `__has_virtual_destructor` はプラットフォーム型でも機能します。また、プラットフォーム型のユーザー定義のデストラクターは仮想デストラクターです。  
  
    ```  
  
    // has_virtual_destructor.cpp  
    #include <stdio.h>  
    struct S {  
    virtual ~S() {}  
    };  
  
    int main() {  
    __has_virtual_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_abstract(` `type` `)`  
  
     型が抽象型である場合は true を返します。 ネイティブ抽象型の詳細については、次を参照してください。[抽象](../windows/abstract-cpp-component-extensions.md)です。  
  
     `__is_abstract` はプラットフォーム型でも機能します。 1 つ以上の抽象メンバーを持つ参照型と同様に、1 つ以上のメンバーを持つインターフェイスは抽象型です。 プラットフォームの種類の詳細については、次を参照してください[抽象クラス。](../cpp/abstract-classes-cpp.md)  
  
    ```  
  
    // is_abstract.cpp  
    #include <stdio.h>  
    struct S {  
    virtual void Test() = 0;  
    };  
  
    int main() {  
    __is_abstract(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_base_of(` `base` `,` `derived` `)`  
  
     最初の型が 2 番目の型の基本クラスの場合、または両方の型が同じ場合は true を返します。  
  
     `__is_base_of` はプラットフォーム型でも機能します。 最初の型が true を返すなど、[インターフェイス クラス](../windows/interface-class-cpp-component-extensions.md)し、2 番目の型がインターフェイスを実装します。  
  
    ```  
  
    // is_base_of.cpp  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    __is_base_of(S, T) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_base_of(S, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_class(` `type` `)`  
  
     型がネイティブ クラスまたは構造体である場合に true を返します。  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_class(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_convertible_to(` `from` `,`  `to` `)`  
  
     最初の型が 2 番目の型に変換できる場合は true を返します。  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    S * s = new S;  
    T * t = new T;  
    s = t;  
    __is_convertible_to(T, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_delegate(` `type` `)`  
  
     `type` がデリゲートである場合は true を返します。 詳細については、次を参照してください。 [delegate (C++ コンポーネント拡張)](../windows/delegate-cpp-component-extensions.md)です。  
  
    ```  
  
    delegate void MyDel();  
    int main() {  
    System::Console::WriteLine(__is_delegate(MyDel));  
    }  
  
    ```  
  
-   `__is_empty(` `type` `)`  
  
     型にインスタンス データ メンバーがない場合に true を返します。  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    int Test() {}  
    static int i;  
    };  
    int main() {  
    __is_empty(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_enum(` `type` `)`  
  
     型がネイティブな列挙型 (Enum) である場合に true を返します。  
  
    ```  
  
    // is_enum.cpp  
    #include <stdio.h>  
    enum E { a, b };  
  
    struct S {  
    enum E2 { c, d };  
    };  
  
    int main() {  
    __is_enum(E) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_enum(S::E2) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_interface_class(` `type` `)`  
  
     プラットフォーム インターフェイスが渡された場合に true を返します。 詳細については、次を参照してください。[インターフェイス クラス](../windows/interface-class-cpp-component-extensions.md)です。  
  
    ```  
  
    // is_interface_class.cpp  
  
    using namespace System;  
    interface class I {};  
    int main() {  
    Console::WriteLine(__is_interface_class(I));  
    }  
  
    ```  
  
-   `__is_pod(` `type` `)`  
  
     型がコンストラクターを持たないクラスまたは共用体、プライベートまたは保護された非静的なメンバー、基本クラス、仮想関数がない場合に true を返します。 POD 型の詳細については、C++ 標準のセクション 8.5.1/1、9/4、3.9/10 を参照してください。  
  
     `__is_pod` は基本型の場合に false を返します。  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_pod(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_polymorphic(` `type` `)`  
  
     ネイティブ型に仮想関数がある場合は true を返します。  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    virtual void Test(){}  
    };  
  
    int main() {  
    __is_polymorphic(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_ref_array(` `type` `)`  
  
     プラットフォーム配列が渡された場合に true を返します。 詳細については、次を参照してください。[配列](../windows/arrays-cpp-component-extensions.md)です。  
  
    ```  
  
    using namespace System;  
    int main() {  
    array<int>^ x = gcnew array<int>(10);  
    Console::WriteLine(__is_ref_array(array<int>));  
    }  
  
    ```  
  
-   `__is_ref_class(` `type` `)`  
  
     参照クラスが渡された場合に true を返します。 ユーザー定義の参照型の詳細については、次を参照してください。[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)です。  
  
    ```  
  
    using namespace System;  
    ref class R {};  
    int main() {  
    Console::WriteLine(__is_ref_class(Buffer));  
    Console::WriteLine(__is_ref_class(R));  
    }  
  
    ```  
  
-   `__is_sealed(` `type` `)`  
  
     プラットフォームが渡された場合、またはネイティブ型が "sealed" に設定されている場合に true を返します。 詳細については、次を参照してください。[シール](../windows/sealed-cpp-component-extensions.md)です。  
  
    ```  
  
    ref class R sealed{};  
    int main() {  
    System::Console::WriteLine(__is_sealed(R));  
    }  
  
    ```  
  
-   `__is_simple_value_class(` `type` `)`  
  
     ガベージ コレクション ヒープへの参照を含まない値の型が渡された場合に true を返します。 ユーザー定義の値型の詳細については、次を参照してください。[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)です。  
  
    ```  
  
    using namespace System;  
    ref class R {};  
    value struct V {};  
    value struct V2 {  
    R ^ r;   // not a simnple value type  
    };  
  
    int main() {  
    Console::WriteLine(__is_simple_value_class(V));  
    Console::WriteLine(__is_simple_value_class(V2));  
    }  
  
    ```  
  
-   `__is_union(` `type` `)`  
  
     型が共用体の場合に true を返します。  
  
    ```  
  
    #include <stdio.h>  
    union A {  
    int i;  
    float f;  
    };  
  
    int main() {  
    __is_union(A) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_value_class(` `type` `)`  
  
     値の型が渡された場合に true を返します。 ユーザー定義の値型の詳細については、次を参照してください。[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)です。  
  
    ```  
  
    value struct V {};  
  
    int main() {  
    System::Console::WriteLine(__is_value_class(V));  
    }  
  
    ```  
  
## <a name="windows-runtime"></a>Windows ランタイム  
 **解説**  
  
 `__has_finalizer(`*型*`)`このプラットフォームがファイナライザーをサポートしていないために、型の特徴がサポートされていません。  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/ZW**  
  
## <a name="common-language-runtime"></a>共通言語ランタイム 
 **解説**  
  
 (この機能のプラットフォーム固有の解説はありません。)  
  
### <a name="requirements"></a>要件  
 コンパイラ オプション: **/clr**  
  
### <a name="examples"></a>使用例  
 **例**  
  
 次のコード例は、クラス テンプレートを使用してのコンパイラ型の特徴を公開する方法を示しています、 **/clr**コンパイルします。 詳細については、次を参照してください。 [Windows ランタイムおよびマネージ テンプレート](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)です。  
  
```  
// compiler_type_traits.cpp  
// compile with: /clr  
using namespace System;  
  
template <class T>  
ref struct is_class {  
   literal bool value = __is_ref_class(T);  
};  
  
ref class R {};  
  
int main () {  
   if (is_class<R>::value)  
      Console::WriteLine("R is a ref class");  
   else  
      Console::WriteLine("R is not a ref class");  
}  
```  
  
 **出力**  
  
```Output  
R is a ref class  
```  
  
## <a name="see-also"></a>関連項目  
 [ランタイム プラットフォームのコンポーネントの拡張機能](../windows/component-extensions-for-runtime-platforms.md)