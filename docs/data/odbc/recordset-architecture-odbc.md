---
title: 'レコード セット: 構造 (ODBC) |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- recordsets, data members
- field data members, recordset architecture
- field data members
- m_nParams data member, recordsets
- recordsets, architecture
- parameter data members in recordsets
- m_nFields data member
- ODBC recordsets, architecture
- m_nParams data member
- m_nFields data member, recordsets
ms.assetid: 47555ddb-11be-4b9e-9b9a-f2931764d298
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 96dfbf9079edefa603a47b73284a4e7fcd8f447c
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338107"
---
# <a name="recordset-architecture-odbc"></a>レコードセット: レコードセットの構造 (ODBC)
このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、レコード セット オブジェクトのアーキテクチャを構成するデータ メンバーについて説明します。  
  
-   [フィールド データ メンバー](#_core_field_data_members)  
  
-   [パラメーター データ メンバー](#_core_parameter_data_members)  
  
-   [M_nFields と m_nParams データ メンバーを使用します。](#_core_using_m_nfields_and_m_nparams)  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない `CRecordset` の派生オブジェクトを対象にしています。 バルク行フェッチが実装されている場合は、アーキテクチャは似ています。 相違点を理解するのを参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
##  <a name="_core_a_sample_class"></a> サンプル クラス  
 使用すると、 [MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md)から**クラスの追加**から派生したレコード セット クラスを宣言するウィザード`CRecordset`、結果として得られるクラスには単純な次に示すように、一般的な構造クラス:  
  
```cpp  
class CCourse : public CRecordset  
{  
public:  
   CCourse(CDatabase* pDatabase = NULL);  
   ...  
   CString m_strCourseID;  
   CString m_strCourseTitle;  
   CString m_strIDParam;  
};  
```  
  
 一連のクラスの先頭には、ウィザードが書き込まれます[フィールド データ メンバーの](#_core_field_data_members)します。 クラスを作成するときに、1 つまたは複数のフィールド データ メンバーを指定する必要があります。 クラスは、パラメーター化のサンプルとクラスが (データ メンバーと`m_strIDParam`)、手動で追加する必要があります[パラメーター データ メンバー](#_core_parameter_data_members)します。 ウィザードでは、クラスに追加のパラメーターはサポートしません。  
  
##  <a name="_core_field_data_members"></a> フィールド データ メンバー  
 レコード セット クラスの最も重要なメンバーは、フィールド データ メンバーです。 各列では、データ ソースから選択するは、クラスには、その列の適切なデータ型のデータ メンバーが含まれています。 たとえば、[サンプル クラス](#_core_a_sample_class)これの冒頭で示したトピックには 2 つのフィールド データ メンバーは、両方の種類の`CString`という`m_strCourseID`と`m_strCourseTitle`します。  
  
 フレームワークが自動的に現在のレコードの列をバインドして、レコード セットが一連のレコードを選択 (後に、`Open`呼び出し、最初のレコードが現在)、オブジェクトのフィールド データ メンバーにします。 これは、フレームワークは、レコードの列の内容を格納するバッファーとして適切なフィールド データ メンバーを使用します。  
  
 ユーザーが新しいレコードをスクロールすると、フレームワークは、現在のレコードを表すため、フィールド データ メンバーを使用します。 フレームワークは、前のレコードの値を置換する、フィールド データ メンバーを更新します。 フィールド データ メンバーは、現在のレコードを更新し、新しいレコードを追加するためにも使用されます。 レコードの更新のプロセスの一環として、適切なフィールド データ メンバーまたはメンバーに直接値を割り当てることで、値の更新を指定します。  
  
##  <a name="_core_parameter_data_members"></a> パラメーター データ メンバー  
 クラスがパラメーター化された場合は、1 つまたは複数のパラメーター データ メンバーを持ちます。 パラメーター化されたクラスを使用して、レコード セットのクエリに基づく情報を取得または実行時に計算できます。  
  
 通常、パラメーターでは、次の例のように、選択範囲を絞り込むことが。 に基づいて、[サンプル クラス](#_core_a_sample_class)このトピックの先頭には、レコード セット オブジェクトは、次の SQL ステートメントを実行します。  
  
```sql  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = ?  
```  
  
 "?"は実行時に指定するパラメーター値のプレース ホルダーです。 レコード セットを構築する際に設定とその`m_strIDParam`MATH101 するデータ メンバー、レコード セットの有効な SQL ステートメントになります。  
  
```sql  
SELECT CourseID, CourseTitle FROM Course WHERE CourseID = MATH101  
```  
  
 パラメーター データ メンバーを定義すると、SQL 文字列内のパラメーターに関する、フレームワークに指示します。 フレームワークは、ODBC のプレース ホルダーを置き換える値を取得する場所を知ることができるパラメーターをバインドします。 例では、結果のレコード セットには、値が MATH101 CourseID 列を Course テーブルからレコードのみが含まれています。 このレコードのすべての指定した列が選択されます。 多くのパラメーター (とプレース ホルダー) を指定するようにする必要があります。  
  
> [!NOTE]
>  MFC は何も自体パラメーターを使用して、具体的には、テキストの置換実行されません。 代わりに、MFC ODBC に伝えます。 パラメーターを取得する場所ODBC では、データを取得し、必要なパラメーター化を実行します。  
  
> [!NOTE]
>  パラメーターの順序が重要です。 これに関する情報とパラメーターの詳細については、次を参照してください。[レコード セット: レコード セット (ODBC) をパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)します。  
  
##  <a name="_core_using_m_nfields_and_m_nparams"></a> M_nFields と m_nParams を使用してください。  

 初期化ウィザードが、クラスのコンス トラクターを書き込むときに、 [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)の数を指定するデータ メンバー[フィールド データ メンバーの](#_core_field_data_members)クラス。 追加する場合[パラメーター](#_core_parameter_data_members) 、クラスの初期化を追加する必要がありますも、 [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)データ メンバーは、パラメーターのデータ メンバーの数を指定します。 フレームワークでは、これらの値を使用して、データ メンバーを使用します。  
  
 詳細と例については、次を参照してください。[レコード フィールド エクス チェンジ: RFX の使い方](../../data/odbc/record-field-exchange-using-rfx.md)します。  
  
## <a name="see-also"></a>関連項目  
 [レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)   
 [レコード セット: テーブル (ODBC) クラスの宣言](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)