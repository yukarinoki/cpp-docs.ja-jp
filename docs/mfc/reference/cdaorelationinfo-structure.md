---
title: CDaoRelationInfo 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoRelationInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0fedf6ad90af670a462b0ccac23cc599a1a13e26
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336359"
---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo 構造体
`CDaoRelationInfo`構造には、2 つのテーブルのフィールドの間で定義されている関係に関する情報が含まれる、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp
struct CDaoRelationInfo  
{  
    CDaoRelationInfo();                     // Constructor  
    CString m_strName;                      // Primary  
    CString m_strTable;                     // Primary  
    CString m_strForeignTable;              // Primary  
    long m_lAttributes;                     // Secondary  
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary  
    short m_nFields;                        // Secondary
    // Below the // Implementation comment:
    // Destructor, not otherwise documented  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
*m_strName*  
 Relation オブジェクトの一意名します。 詳細については、「Name プロパティ」DAO ヘルプのトピックを参照してください。  
  
 *m_strTable*  
 リレーションシップでプライマリ テーブルを名前します。  
  
 *m_strForeignTable*  
 リレーションシップの外部テーブルを名前します。 外部テーブルは、外部キーの格納に使用されるテーブルです。 一般に、外部テーブルを使用して、確立するか、参照整合性を適用します。 外部テーブルは、一対多リレーションシップの"多"側では、通常は。 外部テーブルの例では、アメリカ合衆国の州またはカナダの州や顧客の注文のコードを含むテーブルを含めます。  
  
 *m_lAttributes*  
 リレーションシップの種類についての情報が含まれています。 このメンバーの値には、次のいずれかを指定できます。  
  
- `dbRelationUnique` リレーションシップは一対一です。  
  
- `dbRelationDontEnforce` リレーションシップがない (参照整合性がありません) が適用されます。  
  
- `dbRelationInherited` アタッチされた 2 つのテーブルを含む固定データベース内にリレーションシップが存在します。  
  
- `dbRelationLeft` 関係は、左結合です。 左外部結合には、すべての最初のレコードが含まれます (左側) の 2 つのテーブルでは、値が一致する 2 つ目の (右側) のテーブル内のレコードがない場合でもです。  
  
- `dbRelationRight` リレーションシップは、右外部結合です。 右外部結合には、すべての 2 番目のレコードが含まれます (右側) の 2 つのテーブルでは、値が一致する最初の (左側) のテーブルにレコードがない場合でもです。  
  
- `dbRelationUpdateCascade` 更新プログラムが重ねて表示します。  
  
- `dbRelationDeleteCascade` 削除が重ねて表示します。  
  
*m_pFieldInfos*  
 配列へのポインター [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md)構造体。 配列には、1 つのオブジェクト リレーションシップ内の各フィールドが含まれています。 `m_nFields`データ メンバーが配列の要素の数を示します。  
  
*m_nFields*  
 数`CDaoRelationFieldInfo`内のオブジェクト、`m_pFieldInfos`データ メンバー。  
  
## <a name="remarks"></a>Remarks  
 プライマリとセカンダリの上への参照情報がによって返される方法を示すため、 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)クラスのメンバー関数`CDaoDatabase`します。  
  
 リレーションシップ オブジェクトは、MFC クラスでは表されません。 代わりに、MFC オブジェクトの基になる、DAO オブジェクト、`CDaoDatabase`クラスがリレーションシップ オブジェクトのコレクションを保持:`CDaoDatabase`の関係については、各アイテムにアクセスする装置メンバー関数を使ってアクセスできるすべて一度に、 `CDaoRelationInfo`オブジェクトを呼び出すことによって、`GetRelationInfo`親データベース オブジェクトのメンバー関数。  
  
 によって取得される情報、 [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)にメンバー関数が格納されている、`CDaoRelationInfo`構造体。 `CDaoRelationInfo` 定義、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoRelationInfo`オブジェクト。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [CDaoRelationFieldInfo 構造体](../../mfc/reference/cdaorelationfieldinfo-structure.md)
