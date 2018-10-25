---
title: 'レコード フィールド エクス チェンジ: ウィザード コードの使用 |Microsoft Docs'
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
ms.openlocfilehash: cffd5b262b40fca4814acbd5d0d89d6a6693c814
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070567"
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>レコード フィールド エクスチェンジ: ウィザード コードの操作

このトピックでは、コードを説明する MFC アプリケーション ウィザードと**クラスの追加**(」の説明に従って[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) rfx 関数とそのコードを変更する方法をサポートするために記述します。

> [!NOTE]
>  このトピックの対象から派生したクラス`CRecordset`バルク行フェッチは実装されていません。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクス チェンジ (Bulk RFX) が実装されます。 バルク rfx 関数は、rfx 関数に似ています。 相違点を理解するのを参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。

MFC アプリケーション ウィザードを使用してレコード セット クラスを作成する場合または**クラスの追加**ウィザードでは、テーブル、データ ソースに基づいてして、ウィザードで行った列の選択の RFX に関連する次の要素が書き込まれます。

- レコード セット クラスでは、レコード セット フィールド データ メンバーの宣言

- オーバーライド `CRecordset::DoFieldExchange`

- レコード セット クラスのコンス トラクターでレコード セット フィールド データ メンバーの初期化

##  <a name="_core_the_field_data_member_declarations"></a> フィールド データ メンバーの宣言

ウィザードでは、クラスの次のような .h ファイルでレコード セット クラスの宣言を記述`CSections`:

```cpp
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

パラメーター データ メンバーまたは自分でバインドする新しいフィールド データ メンバーを追加する場合は、ウィザードで生成された規則の後に追加します。

ウィザードをオーバーライドする通知も、`DoFieldExchange`クラスのメンバー関数`CRecordset`します。

##  <a name="_core_the_dofieldexchange_override"></a> メンバーのオーバーライド

[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) RFX の心臓部です。 Framework 呼び出し`DoFieldExchange`いつでもデータ ソースにレコード セットにデータ ソースから、またはレコード セットからデータを移動する必要があります。 `DoFieldExchange` サポートに関する情報を取得するフィールドからのデータ メンバーのも、 [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty)と[調べる](../../mfc/reference/crecordset-class.md#isfieldnull)メンバー関数。

次`DoFieldExchange`オーバーライドは、`CSections`クラス。 ウィザードでは、レコード セット クラスの .cpp ファイルで、関数が書き込まれます。

```cpp
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

関数の次の主要機能に注目してください。

- 関数のこのセクションでは、フィールド マップと呼ばれます。

- 呼び出し`CFieldExchange::SetFieldType`を使用して、`pFX`ポインター。 この呼び出しは、すべての RFX 関数の末尾に呼び出しを指定します`DoFieldExchange`または次回の呼び出し`SetFieldType`は出力列です。 詳細については、次を参照してください。[つ](../../mfc/reference/cfieldexchange-class.md#setfieldtype)します。

- いくつかの呼び出し、`RFX_Text`グローバル関数、フィールド データ メンバーごとに 1 つ (は他のすべて`CString`の例では、変数)。 これらの呼び出しでは、データ ソースに列名とフィールドのデータ メンバー間のリレーションシップを指定します。 RFX 関数は、実際のデータ転送を行います。 クラス ライブラリでは、RFX 関数の一般的なすべてのデータ型を提供します。 RFX 関数の詳細については、次を参照してください。[レコード フィールド エクス チェンジ: RFX 関数を使用して](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)します。

    > [!NOTE]
    >  結果セットの列の順序では、RFX 関数の呼び出しの順序が一致する必要があります`DoFieldExchange`します。

- `pFX`へのポインターを[CFieldExchange](../../mfc/reference/cfieldexchange-class.md)を呼び出すときに、フレームワークが渡すオブジェクト`DoFieldExchange`します。 `CFieldExchange`オブジェクトは、操作を指定しますを`DoFieldExchange`転送、およびその他のコンテキスト情報の方向を実行することです。

##  <a name="_core_the_recordset_constructor"></a> レコード セットのコンス トラクター

ウィザードが作成するレコード セットのコンス トラクターには、RFX に関連する次の 2 つが含まれています。

- 各フィールド データ メンバーの初期化

- 初期化、 [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)フィールド データ メンバーの数を格納するデータ メンバー

コンス トラクター、`CSections`次のようなレコード セットの使用例。

```cpp
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
>  インクリメントする必要がありますフィールド データ メンバーを新しい列を動的にバインドする場合、手動で追加する場合`m_nFields`します。 など、コードの別の行を追加して、操作を行います。

```cpp
m_nFields += 3;
```

これは、次の 3 つの新しいフィールドを追加するコードです。 初期化する必要があります、パラメーターのデータ メンバーを追加する場合、 [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)データ メンバーは、パラメーターのデータ メンバーの数が含まれています。 配置、`m_nParams`かっこの外側に初期化します。

## <a name="see-also"></a>関連項目

[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)