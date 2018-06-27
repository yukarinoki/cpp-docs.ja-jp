---
title: 'TN043: RFX ルーチン |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- RFX
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), architecture
- TN043
- RFX (record field exchange)
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc6556cabaa8f1f04a2a53771b495233620e1a14
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954410"
---
# <a name="tn043-rfx-routines"></a>テクニカル ノート 43: RFX ルーチン
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 ここではレコード フィールド エクス (チェンジ RFX) アーキテクチャについて説明します。 また、記述する方法について説明、 **rfx _** プロシージャです。  
  
## <a name="overview-of-record-field-exchange"></a>レコード フィールド エクス チェンジの概要  
 すべてのレコード セット フィールド関数は、C++ コードによって実行されます。 マクロや特別なリソースはありません。 機構の中心となるは、仮想関数すべてのレコード セットの派生クラスでオーバーライドする必要があります。 このフォームに常に存在します。  
  
```  
void CMySet::DoFieldExchange(CFieldExchange* pFX)  
{ *//{{AFX_FIELD_MAP(CMySet)  
 <recordset exchange field type call>  
 <recordset exchange function call> *//}}AFX_FIELD_MAP  
}  
```  
  
 特殊なフォーマット AFX コメントでは、ClassWizard を探して、この関数内でコードを編集できるようにします。 ClassWizard と互換性がないコードは、特殊な形式のコメントの外側に配置する必要があります。  
  
 上記の例では、< recordset_exchange_field_type_call > の形式は。  
  
```  
pFX->SetFieldType(CFieldExchange::outputColumn);
```  
  
 および < recordset_exchange_function_call > で、フォームには。  
  
```  
RFX_Custom(pFX, "Col2",
    m_Col2);
```  
  
 ほとんど**rfx _** 関数がある 3 つ、上記のように引数がいくつか (例:`RFX_Text`と`RFX_Binary`) その他の省略可能な引数があります。  
  
 1 つ以上**rfx _** それぞれに含めることは`DoDataExchange`関数。  
  
 すべてのレコード セット フィールド exchange ルーチン MFC に用意されているの一覧については、' afxdb.h' を参照してください。  
  
 レコード セットのフィールドの呼び出しは、フィールドのデータを格納するメモリ位置 (通常はデータ メンバー) を登録する方法、`CMySet`クラスです。  
  
## <a name="notes"></a>メモ  
 レコード セット フィールド関数でのみ機能するように設計されています、`CRecordset`クラスです。 その他の MFC クラスで一般的に使用可能なことはできません。  
  
 データの初期値は、標準 C++ のコンス トラクターで、通常のブロック設定`//{{AFX_FIELD_INIT(CMylSet)`と`//}}AFX_FIELD_INIT`コメントです。  
  
 各**rfx _** 関数は、フィールドのダーティ状態を準備するため、フィールドを編集するためにフィールドをアーカイブに戻るまで、さまざまな操作をサポートする必要があります。  
  
 各関数を呼び出す`DoFieldExchange`(たとえば`SetFieldNull`、 `IsFieldDirty`)、初期化呼び出しの周囲には`DoFieldExchange`します。  
  
## <a name="how-does-it-work"></a>動作方法  
 レコード フィールド エクス チェンジを使用するために、次を理解する必要はありません。 ただし、バック グラウンドでこの処理に役立つについては、独自 exchange プロシージャを記述します。  
  
 `DoFieldExchange`メンバー関数は、非常によく似た、`Serialize`メンバー関数は、-を取得または送信元/送信先クラスのメンバー データに/(ODBC クエリの結果からケース列がこの) 内の外部のフォームからデータを設定します。 *PFX*パラメーターのデータ交換を行うためのコンテキストし、似ています、 *CArchive*パラメーターを`CObject::Serialize`です。 *PFX* (、`CFieldExchange`オブジェクト) を持ち、操作に似ていますが、インジケーターはの汎化、 *CArchive*方向フラグ。 RFX 関数は、次の操作をサポートする必要があります。  
  
- `BindParam` — 示す ODBC がパラメーターのデータを取得する必要があります。  
  
- `BindFieldToColumn` -場所 ODBC 必要があります取得/預金 outputColumn データを指定します。  
  
- `Fixup` -設定`CString/CByteArray`の長さは、NULL 状態ビットを設定します。  
  
- `MarkForAddNew` 、AddNew を呼び出すので、値が変更された場合マークがダーティします。  
  
- `MarkForUpdate` 、編集を呼び出すので、値が変更された場合マークがダーティします。  
  
- `Name` — マークされているフィールドの名前を追加します。  
  
- `NameValue` -追加"\<列名 > ="マークされているフィールドの  
  
- `Value` -追加""などの区切り文字の後に、',' または ' '  
  
- `SetFieldDirty` ステータス ビット ダーティ (つまり変更された) フィールドを設定します。  
  
- `SetFieldNull` フィールドの null 値を示すステータス ビットを設定します。  
  
- `IsFieldDirty` : ダーティ状態のビットの戻り値  
  
- `IsFieldNull` -Null 状態ビットの値を返す  
  
- `IsFieldNullable` — フィールドが NULL 値を保持できる場合は TRUE を返す  
  
- `StoreField` : アーカイブ フィールドの値  
  
- `LoadField` アーカイブ済みのフィールドの値を再読み込み  
  
- `GetFieldInfoValue` 、フィールドに関する一般情報は戻り値  
  
- `GetFieldInfoOrdinal` 、フィールドに関する一般情報は戻り値  
  
## <a name="user-extensions"></a>ユーザーの拡張機能  
 既定の RFX 機構を拡張するいくつかの方法はあります。 できます  
  
-   新しいデータ型を追加します。 例えば:  
  
 ```  
    CBookmark 
 ```  
  
-   新しい exchange プロシージャ (rfx _) を追加します。  
  
 ```  
    void AFXAPI RFX_Bigint(CFieldExchange* pFX,
    const char *szName,  
    BIGINT& value);

 ```  
  
-   `DoFieldExchange`メンバー関数は rfx 関数呼び出しの追加、またはその他の有効な C++ ステートメントに条件付きでインクルードされます。  
  
 ```  
    while (posExtraFields != NULL)  
 {  
    RFX_Text(pFX,
    m_listName.GetNext(posExtraFields),   
    m_listValue.GetNext(posExtraValues));

 }  
 ```  
  
> [!NOTE]
>  このようなコードは ClassWizard で編集することはできず、特殊な形式のコメントの外側でのみ使用する必要があります。  
  
## <a name="writing-a-custom-rfx"></a>カスタム RFX の書き込み  
 独自のカスタム RFX 関数を書き込みは、既存の RFX 関数をコピーして、独自の目的に変更するをお勧めします。 コピーする右の RFX を選択する関数を作成できますはるかに簡単です。 一部の RFX 関数プロパティを持ついくつか一意のコピー先を決定する際に考慮します。  
  
 `RFX_Long` `RFX_Int`:  
 これらは、最も単純な RFX 関数です。 データ値が、何らかの解釈を必要はありませんし、データのサイズは固定します。  
  
 `RFX_Single` `RFX_Double`:  
 RFX_Long や RFX_Int 上記のようにこれらの関数は、シンプルで行うことができます、既定の実装の広範囲に使用します。 保存されているように、dbrfx.cpp ではなくでただし、浮動小数点ライブラリを明示的に参照されている場合にのみ、ランタイムの読み込みを有効にします。  
  
 `RFX_Text` `RFX_Binary`:  
 これら 2 つの関数は、文字列またはバイナリ情報を保持する静的バッファーを事前に割り当てるし、ODBC SQLBindCol に登録すると値の代わりにこれらのバッファーを登録する必要があります。 このためは、これら 2 つの関数は、特殊なコードの多くがあります。  
  
 `RFX_Date`:  
 ODBC では、独自の TIMESTAMP_STRUCT データ構造で日付と時刻の情報を返します。 この関数では、「プロキシ」として、TIMESTAMP_STRUCT が動的に日付時刻データを送受信するために割り当てます。 さまざまな操作は、C++ の間で日付と時刻の情報を転送する必要があります`CTime`オブジェクトおよび TIMESTAMP_STRUCT プロキシ。 この関数、かなり複雑ですが、データの転送にプロキシを使用する方法の良い例。  
  
 `RFX_LongBinary`:  
 これは、唯一のクラス ライブラリのデータを送受信する列のバインドを使用しない RFX 関数です。 この関数は BindFieldToColumn 操作を無視し、代わりに、フィックス アップ操作中に受信 SQL_LONGVARCHAR または SQL_LONGVARBINARY データを保持するためにストレージを割り当てます、割り当てられているストレージに値を取得するための SQLGetData 呼び出しを実行します。 、(NameValue と値の操作) などのデータ ソースへのデータ値を返信する準備が整ったときに、この関数は、ODBC の DATA_AT_EXEC 機能を使用します。 参照してください[テクニカル ノート 45](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) SQL_LONGVARBINARY データ型と SQL_LONGVARCHARs の操作方法の詳細。  
  
 独自の書き込み時に**rfx _** 関数の場合、多くの場合、ことができますを使用する`CFieldExchange::Default`特定の操作を実装します。 問題の操作の既定の実装を確認します。 操作を実行する場合とで記述した、 **rfx _** 関数に委任することができます、`CFieldExchange::Default`です。 呼び出し元の例を確認できます`CFieldExchange::Default`dbrfx.cpp で  
  
 呼び出すことが重要`IsFieldType`RFX 関数と FALSE を返す場合にすぐに戻り値の開始時にします。 このメカニズムで実行されているパラメーターの操作を保持する*outputColumns*、およびその逆 (呼び出しのような`BindParam`上、 *outputColumn*)。 さらに、`IsFieldType`自動的には、追跡のカウント*outputColumns* (*m_nFields*) とパラメーター (*m_nParams*)。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

