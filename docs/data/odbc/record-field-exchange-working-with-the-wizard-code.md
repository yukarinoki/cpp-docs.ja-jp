---
title: 'レコード フィールド エクス チェンジ: ウィザード コードの使用 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DoFieldExchange method, overriding
- Unicode, with database classes
- field data members, declaring
- RFX (ODBC), wizard code
- RFX (ODBC), implementing
- field data members
- ODBC, RFX
- m_nParams data member, initializing
- m_nFields data member
- m_nParams data member
- overriding, DoFieldExchange
- m_nFields data member, initializing
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d4f817ebfc3e6bb72865b4fc71fd5c5ebe5f671
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092510"
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>レコード フィールド エクスチェンジ: ウィザード コードの操作
このトピックのコードを MFC アプリケーション ウィザードと**クラスの追加**(」の説明に従って[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) RFX とそのコードを変更する方法をサポートするために記述します。  
  
> [!NOTE]
>  このトピックの対象から派生したクラス`CRecordset`バルク行フェッチは実装されていません。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクス チェンジ (Bulk RFX) が実装されます。 バルク rfx 関数は rfx 関数に似ています。 相違点を理解するのを参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
 MFC アプリケーション ウィザードを使用して、レコード セット クラスを作成する場合または**クラスの追加**、テーブルをデータ ソースに基づくし、ウィザードで行った列の選択の RFX に関連する次の要素が書き込まれます。  
  
-   レコード セット クラスでは、レコード セット フィールド データ メンバーの宣言  
  
-   オーバーライド `CRecordset::DoFieldExchange`  
  
-   レコード セット クラスのコンス トラクターでレコード セットのフィールド データ メンバーの初期化  
  
##  <a name="_core_the_field_data_member_declarations"></a> フィールド データ メンバーの宣言  
 ウィザードは、クラスの次のような .h ファイルでレコード セット クラスの宣言を書き込む`CSections`:  
  
```  
class CSections : public CRecordset  
{  
public:  
   CSections(CDatabase* pDatabase = NULL);  
   DECLARE_DYNAMIC(CSections)  
  
// Field/Param Data  
   CString   m_strCourseID;  
   CString   m_strInstructorID;  
   CString   m_strRoomNo;  
   CString   m_strSchedule;  
   CString   m_strSectionNo;  
  
// Overrides  
   // Wizard generated virtual function overrides  
   protected:  
   virtual CString GetDefaultConnect();  // Default connection string  
   virtual CString GetDefaultSQL();      // Default SQL for Recordset  
   virtual void DoFieldExchange(CFieldExchange* pFX);  // RFX support  
  
// Implementation  
#ifdef _DEBUG  
   virtual void AssertValid() const;  
   virtual void Dump(CDumpContext& dc) const;  
#endif  
  
};  
```  
  
 パラメーター データ メンバーまたは自分でバインドする新しいフィールド データ メンバーを追加する場合は、ウィザードで生成されたものの後に追加します。  
  
 またに注意してください、ウィザードをオーバーライドする、`DoFieldExchange`クラスのメンバー関数`CRecordset`です。  
  
##  <a name="_core_the_dofieldexchange_override"></a> DoFieldExchange 上書き  

 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) RFX の中心となるはします。 フレームワークによって`DoFieldExchange`いつでもデータ ソースに、レコード セットへのデータ ソースまたはレコード セットからデータを移動する必要があります。 `DoFieldExchange` サポートに関する情報の取得がを通じてデータ メンバーをフィールドも、 [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty)と[調べる](../../mfc/reference/crecordset-class.md#isfieldnull)メンバー関数。  
  
 次`DoFieldExchange`オーバーライドは、`CSections`クラスです。 ウィザードでは、レコード セット クラスの .cpp ファイルで関数を書き込みます。  
  
```  
void CSections::DoFieldExchange(CFieldExchange* pFX)  
{  
   pFX->SetFieldType(CFieldExchange::outputColumn);  
   RFX_Text(pFX, "CourseID", m_strCourseID);  
   RFX_Text(pFX, "InstructorID", m_strInstructorID);  
   RFX_Text(pFX, "RoomNo", m_strRoomNo);  
   RFX_Text(pFX, "Schedule", m_strSchedule);  
   RFX_Text(pFX, "SectionNo", m_strSectionNo);  
}  
```  
  
 関数の次の主要機能を確認してください。  
  
-   関数のこのセクションでは、フィールド マップと呼ばれます。  
  
-   呼び出し`CFieldExchange::SetFieldType`して、`pFX`ポインター。 この呼び出しは、すべて RFX 関数の末尾に呼び出しを指定します`DoFieldExchange`かを次に呼び出した`SetFieldType`は出力列です。 詳細については、次を参照してください。[つ](../../mfc/reference/cfieldexchange-class.md#setfieldtype)です。  
  
-   複数回呼び出します、`RFX_Text`グローバル関数、フィールド データ メンバーごとに 1 つ (はすべて`CString`変数の例で)。 これらの呼び出しでは、データ ソースの列名は、フィールド データ メンバーとの間のリレーションシップを指定します。 RFX 関数は、実際のデータ転送を行います。 クラス ライブラリには、すべての一般的なデータ型の RFX 関数が用意されています。 RFX 関数の詳細については、次を参照してください。[レコード フィールド エクス チェンジ: RFX 関数の使い方](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)です。  
  
    > [!NOTE]
    >  結果セットの列の順序は RFX 関数呼び出しの順序と一致する必要があります`DoFieldExchange`です。  
  
-   `pFX`へのポインター、 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)を呼び出すときにフレームワークが渡されるオブジェクト`DoFieldExchange`です。 `CFieldExchange`オブジェクトは、操作を指定する`DoFieldExchange`は、転送、およびその他のコンテキスト情報の方向を実行します。  
  
##  <a name="_core_the_recordset_constructor"></a> レコード セットのコンス トラクター  
 ウィザードが作成するレコード セットのコンス トラクターには、RFX に関連する次の 2 つが含まれています。  
  
-   各フィールド データ メンバーの初期化  
  
-   初期化、 [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)データ メンバーは、フィールド データ メンバーの数が含まれています  
  
 コンス トラクター、`CSections`レコード セットの例は、次のように検索します。  
  
```  
CSections::CSections(CDatabase* pdb)  
   : CRecordset(pdb)  
{  
   m_strCourseID = "";  
   m_strInstructorID = "";  
   m_strRoomNo = "";  
   m_strSchedule = "";  
   m_strSectionNo = "";  
   m_nFields = 5;  
}  
```  
  
> [!NOTE]
>  フィールド データ メンバーを新しい列を動的に連結する場合、手動で追加する場合、必要がありますをインクリメントする`m_nFields`です。 など、コードの別の行を追加することでを実行します。  
  
```  
m_nFields += 3;  
```  

 これは、次の 3 つの新しいフィールドの追加のコードです。 初期化する必要がありますパラメーター データ メンバーを追加する場合、 [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)データ メンバーは、パラメーター データ メンバーの数が含まれています。 Put、`m_nParams`かっこの外側に初期化します。  

  
## <a name="see-also"></a>関連項目  
 [レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)