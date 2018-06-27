---
title: CDaoRelationInfo 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: a49bdfb00c3f2ceba424af7bfdfa652cacec929e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951293"
---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo 構造体
`CDaoRelationInfo`構造体には、2 つのテーブルのフィールドの間で定義されている関係に関する情報が含まれています、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoRelationInfo  
{  
    CDaoRelationInfo();
*// Constructor  
    CString m_strName;      // Primary  
    CString m_strTable;     // Primary  
    CString m_strForeignTable;              // Primary  
    long m_lAttributes;     // Secondary  
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary  
    short m_nFields;        // Secondary *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 *m_strName*  
 Relation オブジェクトの一意名します。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 *m_strTable*  
 リレーションシップの主テーブルを名前します。  
  
 *m_strForeignTable*  
 リレーションシップの外部テーブルを名前します。 外部テーブルは、外部キーの格納に使用されるテーブルです。 一般に、外部テーブルを使用して、確立するか、参照整合性を適用します。 外部テーブルは、一対多リレーションシップの"多"側で通常です。 外部テーブルの例では、アメリカ合衆国の州またはカナダの州や顧客の注文のコードを含むテーブルを含めます。  
  
 *m_lAttributes*  
 リレーションシップの種類についての情報が含まれています。 このメンバーの値には、次のいずれかを指定できます。  
  
- **dbRelationUnique**リレーションシップは一対一です。  
  
- **dbRelationDontEnforce**関係はありません (参照整合性がありません) を適用します。  
  
- **dbRelationInherited**リレーションシップが 2 つの接続されているテーブルを含む固定データベースに存在します。  
  
- **dbRelationLeft**リレーションシップは、左結合します。 左外部結合には、すべての最初のレコードが含まれています (左側) の 2 つのテーブルでは、2 つ目の (右側) のテーブル内のレコードに一致する値がない場合でもです。  
  
- **dbRelationRight**関係は、右外部結合します。 右外部結合には、すべての 2 番目のレコードが含まれます (右側) の 2 つのテーブル (左側) の最初のテーブル内のレコードに一致する値がない場合でもです。  
  
- **これら**が連鎖的に更新します。  
  
- **dbRelationDeleteCascade**が連鎖的に削除します。  
  
 *m_pFieldInfos*  
 配列へのポインター [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md)構造体。 配列には、リレーションシップ内の各フィールドの 1 つのオブジェクトが含まれています。 *M_nFields*データ メンバーは、配列要素の数を示します。  
  
 *m_nFields*  
 数`CDaoRelationFieldInfo`内のオブジェクト、 *m_pFieldInfos*データ メンバーです。  
  
## <a name="remarks"></a>Remarks  
 プライマリとセカンダリ上への参照は、情報がによって返される方法を示すため、 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)クラスのメンバー関数`CDaoDatabase`です。  
  
 リレーションシップ オブジェクトは、MFC クラスでは表されません。 代わりに、MFC オブジェクトの基になる DAO オブジェクトを使用して、`CDaoDatabase`クラス関係オブジェクトのコレクションを保持する:`CDaoDatabase`関係については、の各アイテムにアクセスするメンバー関数を提供して一度にすべてを使ってアクセスできる、 `CDaoRelationInfo`オブジェクトを呼び出して、`GetRelationInfo`親データベース オブジェクトのメンバー関数。  
  
 によって取得される情報、 [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)メンバー関数は、`CDaoRelationInfo`構造体。 `CDaoRelationInfo` 定義、`Dump`デバッグでメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoRelationInfo`オブジェクト。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [CDaoRelationFieldInfo 構造体](../../mfc/reference/cdaorelationfieldinfo-structure.md)
