---
title: リスト ボックスから 2 番目のレコード セット (MFC データ アクセス) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, filling list boxes
- list boxes, filling from second recordset
- recordsets [C++], filling list boxes or combo boxes
- CComboBox class, filling object from second rowset
- ODBC recordsets [C++], filling list boxes or combo boxes
- combo boxes [C++], filling from second recordset
- CListCtrl class, filling from second recordset
ms.assetid: 360c0834-da6b-4dc0-bcea-80e9acd611f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ed294527b4335459ab6d0658d9f57a5cb64a8fd1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090659"
---
# <a name="filling-a-list-box-from-a-second-recordset--mfc-data-access"></a>セカンド レコードセットを利用してリスト ボックスを表示する方法 (MFC データ アクセス)
既定では、1 つのレコード ビューは 1 つのレコードセット オブジェクトに関連付けられ、そのオブジェクトのフィールドがレコード ビューのコントロールに対応付けられます。 場合によっては、レコード ビューにリスト ボックス コントロールまたはコンボ ボックス コントロールを配置して、そこに別の (セカンド) レコードセット オブジェクトの複数の値を設定することが必要となります。 ユーザーは、そのリスト ボックスを使用して、レコード ビューに表示された新しいカテゴリの情報を選択できます。 このトピックでは、いつどのようにこの処理を実行するかについて説明します。  
  
> [!TIP]
>  コンボ ボックスまたはリスト ボックスにデータ ソースから値を設定すると、処理が遅くなることがあります。 多数のレコードを含むレコードセットからコントロールに値を設定しようとする場合は、注意が必要です。  
  
 このトピックで使用するモデルは、フォームのコントロールに値を設定するメイン レコードセットと、リスト ボックスまたはコンボ ボックスに値を設定するセカンド レコードセットで構成されます。 リスト ボックスから文字列を選択すると、その文字列に基づいてメイン レコードセットのクエリが再実行されるようにプログラミングされています。 次の手順ではコンボ ボックスを使用しますが、リスト ボックスの場合も同様です。  
  
#### <a name="to-fill-a-combo-box-or-list-box-from-a-second-recordset"></a>セカンド レコードセットからコンボ ボックスまたはリスト ボックスの値を設定するには  
  
1.  レコード セット オブジェクトを作成 ([CRecordset](../mfc/reference/crecordset-class.md)です。  
  
2.  ポインターを取得、 [CComboBox](../mfc/reference/ccombobox-class.md)コンボ ボックス コントロールのオブジェクト。  
  
3.  コンボ ボックスの以前の内容をすべて空にします。  
  
4.  レコード セット内のすべてのレコードを移動を呼び出す[ccombobox::addstring](../mfc/reference/ccombobox-class.md#addstring)の現在のレコードをコンボ ボックスに追加する各文字列。  
  
5.  コンボ ボックスの選択内容を初期化します。  
  
```  
void CSectionForm::OnInitialUpdate()  
{  
    // ...  
  
    // Fill the combo box with all of the courses  
    CENROLLDoc* pDoc = GetDocument();  
    if (!pDoc->m_courseSet.Open())  
        return;  
  
    // ...  
  
    m_ctlCourseList.ResetContent();  
    if (pDoc->m_courseSet.IsOpen())  
    {   
        while (!pDoc->m_courseSet.IsEOF() )  
        {  
            m_ctlCourseList.AddString(  
                pDoc->m_courseSet.m_CourseID);  
            pDoc->m_courseSet.MoveNext();  
        }  
    }  
    m_ctlCourseList.SetCurSel(0);  
}  
```  
  
 この関数では、提供されるコースごとに 1 つのレコードを含むセカンド レコードセット `m_courseSet` と、レコード ビュー クラスに格納された `CComboBox` コントロール `m_ctlCourseList` を使用しています。  
  
 この関数は、ドキュメントから `m_courseSet` を取得して開きます。 次に、`m_ctlCourseList` を空にして、`m_courseSet` を 1 レコードずつ処理します。 各レコードに対してコンボ ボックスの `AddString` メンバー関数が呼び出されて、レコードからコース ID 値が追加されます。 最後に、コンボ ボックスの選択内容が設定されます。  
  
## <a name="see-also"></a>関連項目  
 [レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)