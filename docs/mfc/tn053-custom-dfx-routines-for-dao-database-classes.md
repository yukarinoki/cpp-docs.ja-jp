---
title: テクニカル ノート 53:DAO データベースクラスのカスタム DFX ルーチン
ms.date: 09/17/2019
helpviewer_keywords:
- MFC, DAO and
- database classes [MFC], DAO
- DAO [MFC], MFC
- DFX (DAO record field exchange) [MFC], custom routines
- TN053
- DAO [MFC], classes
- DFX (DAO record field exchange) [MFC]
- custom DFX routines [MFC]
ms.assetid: fdcf3c51-4fa8-4517-9222-58aaa4f25cac
ms.openlocfilehash: 949e1a07b2b45b01b08efb368046e0c65b1264e1
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095988"
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>テクニカル ノート 53:DAO データベースクラスのカスタム DFX ルーチン

> [!NOTE]
>  DAO は Access データベースで使用され、Office 2013 でサポートされています。 3.6 は最終バージョンであり、廃止されたと見なされます。 ビジュアルC++環境とウィザードでは、dao はサポートされていません (dao クラスは含まれていますが、引き続き使用できます)。 新しいプロジェクトには、 [OLE DB テンプレート](../data/oledb/ole-db-templates.md)または[ODBC および MFC](../data/odbc/odbc-and-mfc.md)を使用することをお勧めします。 既存のアプリケーションを維持するには、DAO のみを使用する必要があります。

このテクニカルノートでは、DAO レコードフィールドエクスチェンジ (DFX) メカニズムについて説明します。 DFX ルーチンの動作を理解するために、関数に`DFX_Text`ついて詳しく説明します。 このテクニカルノートに関するその他の情報源として、他の各 DFX 関数のコードを調べることができます。 (ODBC データベースクラスで使用される) カスタム RFX ルーチンが必要になることが多いため、カスタム DFX ルーチンは必要ありません。

このテクニカルノートには次のものが含まれます。

- DFX の概要

- DAO レコードフィールドエクスチェンジと動的バインドの使用[例](#_mfcnotes_tn053_examples)

- [DFX の動作](#_mfcnotes_tn053_how_dfx_works)

- [カスタム DFX ルーチンの機能](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)

- [DFX_Text の詳細](#_mfcnotes_tn053_details_of_dfx_text)

**DFX の概要**

DAO レコードフィールド交換機構 (DFX) を使用すると、 `CDaoRecordset`クラスを使用してデータを取得および更新する手順を簡略化できます。 このプロセスは、 `CDaoRecordset`クラスのデータメンバーを使用して簡略化されます。 から`CDaoRecordset`派生することにより、テーブルまたはクエリの各フィールドを表す派生クラスにデータメンバーを追加できます。 この "静的バインド" 機構は単純ですが、すべてのアプリケーションで選択できるデータフェッチ/更新方法ではない可能性があります。 DFX は、現在のレコードが変更されるたびに、すべてのバインドフィールドを取得します。 通貨が変更されたときにすべてのフィールドをフェッチする必要のない、パフォーマンスが重視されるアプリケーションを開発`CDaoRecordset::GetFieldValue`し`CDaoRecordset::SetFieldValue`ている場合は、およびを使用した "動的バインド" が選択されたデータアクセス方法になることがあります。

> [!NOTE]
>  DFX と動的バインドは相互に排他的ではないため、静的なバインディングと動的バインドを組み合わせて使用できます。

## <a name="_mfcnotes_tn053_examples"></a>例 1-DAO レコードフィールドの Exchange のみを使用する

(想定`CDaoRecordset` : 派生クラス`CMySet`は既に開いています)

```
// Add a new record to the customers table
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```

**例 2-動的バインドのみを使用する**

`CDaoRecordset` (`rs`クラスを使用することを前提としています。これは既に開いています)

```
// Add a new record to the customers table
COleVariant  varFieldValue1 (_T("MSFT"),
    VT_BSTRT);

//Note: VT_BSTRT flags string type as ANSI,
    instead of UNICODE default
COleVariant  varFieldValue2  (_T("Microsoft"),
    VT_BSTRT);

rs.AddNew();

rs.SetFieldValue(_T("Customer_ID"),
    varFieldValue1);

rs.SetFieldValue(_T("Customer_Name"),
    varFieldValue2);

rs.Update();
```

**例 3: DAO レコードフィールドエクスチェンジと動的バインドの使用**

(は、から派生し`CDaoRecordset`たクラス`emp`を使用して従業員データを参照することを前提とします

```
// Get the employee's data so that it can be displayed
emp.MoveNext();

// If user wants to see employee's photograph,
// fetch it
COleVariant varPhoto;
if (bSeePicture)
    emp.GetFieldValue(_T("photo"),
    varPhoto);

// Display the data
PopUpEmployeeData(emp.m_strFirstName,
    emp.m_strLastName,
    varPhoto);
```

## <a name="_mfcnotes_tn053_how_dfx_works"></a>DFX の動作

DFX 機構は、MFC ODBC クラスで使用される RFX (レコードフィールドエクスチェンジ) メカニズムと同様の方法で動作します。 DFX と RFX の原理は同じですが、内部には多くの違いがあります。 DFX 関数の設計は、事実上すべてのコードが個々の DFX ルーチンによって共有されるようになっていました。 最高レベルの DFX では、いくつかの処理が行われます。

- 必要に応じて、DFX によって SQL **SELECT**句と sql **PARAMETERS**句が作成されます。

- DFX は、DAO の`GetRows`関数によって使用されるバインディング構造を構築します (これについては後で詳しく説明します)。

- DFX は、ダーティフィールドを検出するために使用されるデータバッファーを管理します (ダブルバッファリングが使用されている場合)

- DFX は、 **NULL**および**ダーティ**状態の配列を管理し、更新時に必要に応じて値を設定します。

DFX 機構の中核となるのは`CDaoRecordset` 、派生クラスの`DoFieldExchange`関数です。 この関数は、適切な操作の種類の個々の DFX 関数への呼び出しをディスパッチします。 内部 MFC `DoFieldExchange`関数を呼び出す前に、操作の種類を設定します。 次の一覧に、さまざまな操作の種類と簡単な説明を示します。

|操作|説明|
|---------------|-----------------|
|`AddToParameterList`|ビルドパラメーター句|
|`AddToSelectList`|SELECT 句のビルド|
|`BindField`|バインド構造を設定します|
|`BindParam`|パラメーター値の設定|
|`Fixup`|NULL 状態を設定します|
|`AllocCache`|ダーティチェックのためにキャッシュを割り当てます|
|`StoreField`|現在のレコードをキャッシュに保存します|
|`LoadField`|キャッシュをメンバー値に復元します|
|`FreeCache`|キャッシュの解放|
|`SetFieldNull`|フィールドの状態 & 値を NULL に設定します|
|`MarkForAddNew`|擬似 NULL ではない場合、フィールドをダーティとしてマークします|
|`MarkForEdit`|キャッシュに一致しない場合、フィールドがダーティとマークされます|
|`SetDirtyField`|ダーティとマークされたフィールド値を設定します|

次のセクションでは、各操作の詳細について`DFX_Text`説明します。

DAO レコードフィールドの交換プロセスについて理解する最も重要な機能は、 `GetRows` `CDaoRecordset`オブジェクトの関数を使用することです。 DAO `GetRows`関数は、いくつかの方法で動作します。 このテクニカルノートでは、この`GetRows`テクニカルノートの範囲外であるため、簡単に説明します。
DAO 3.6 は最終バージョンであり、互換性のために残されているものと見なされます。 `GetRows`では、いくつかの方法で作業できます。

- 複数のレコードと複数のデータフィールドを一度にフェッチできます。 これにより、大規模なデータ構造を処理し、各フィールドへの適切なオフセットと、構造内のデータの各レコードに対して適切なオフセットを行うことにより、データアクセスを高速化できます。 MFC では、この複数のレコードフェッチメカニズムを利用していません。

- 別の`GetRows`方法として、プログラマがデータの1つのレコードについて、各フィールドの取得データにバインドアドレスを指定できるようにすることもできます。

- また、呼び出し元がメモリを割り当てることができるように、DAO は可変長列の呼び出し元に "コールバック" します。 この2つ目の機能には、データのコピー数を最小限に抑えると共に、クラスのメンバー ( `CDaoRecordset`派生クラス) にデータを直接格納できるという利点があります。 この2番目の機構は、MFC が派生クラスの`CDaoRecordset`データメンバーにバインドするために使用するメソッドです。

##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a>カスタム DFX ルーチンの機能

ここでは、任意の DFX 関数で実装される最も重要な操作が、正常にを呼び出す`GetRows`ために必要なデータ構造を設定する機能である必要があることについて説明します。 DFX 関数がサポートする必要があるその他の操作は多数ありますが、 `GetRows`呼び出しの準備として、重要なものでも複雑でもありません。

DFX の使用方法については、オンラインドキュメントを参照してください。 基本的に、2つの要件があります。 最初に、バインドされたフィールド`CDaoRecordset`とパラメーターごとに、派生クラスにメンバーを追加する必要があります。 この`CDaoRecordset::DoFieldExchange`後に続くをオーバーライドする必要があります。 メンバーのデータ型が重要であることに注意してください。 データベース内のフィールドのデータと一致するか、少なくともその型に変換可能である必要があります。 たとえば、長整数などのデータベース内の数値フィールドは、常にテキストに変換して`CString`メンバーにバインドできますが、データベース内のテキストフィールドは必ずしも数値表現に変換されるとは限りません。長整数などの長整数メンバーにバインドされています。 DAO および Microsoft Jet データベースエンジンは、(MFC ではなく) 変換を担当します。

##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a>DFX_Text の詳細

前に説明したように、DFX の動作を説明する最善の方法は、例を使って作業することです。 このため、の`DFX_Text`内部構造は、少なくとも DFX の基本的な知識を提供するのに役立ちます。

- `AddToParameterList`

   この操作では、 Jet で必要と`Parameters <param name>, <param type> ... ;`される SQL PARAMETERS 句 ("") を構築します。 各パラメーターには、RFX 呼び出しで指定されているように、という名前が付けられます。 個々の型`CDaoFieldExchange::AppendParamType`の名前を確認するには、関数関数を参照してください。 の`DFX_Text`場合、使用される型は**text**です。

- `AddToSelectList`

   SQL **SELECT**句を構築します。 これは、DFX 呼び出しで指定された列名が単に追加されて`SELECT <column name>, ...`いる ("") ため、非常に簡単です。

- `BindField`

   操作の最も複雑な部分。 前述のように、ここでは、で`GetRows`使用される DAO バインド構造がセットアップされています。 構造内の情報の`DFX_Text`型に含まれているコードからわかるように、使用される DAO 型 (の`DFX_Text`場合は**DAO_CHAR**または**DAO_WCHAR** ) が含まれます。 また、使用されるバインディングの種類も設定されます。 以前のセクション`GetRows`では、簡単に説明しましたが、MFC で使用されるバインディングの型は常にダイレクトアドレスのバインド (**DAOBINDING_DIRECT**) であることを説明するだけで十分でした。 また、可変長の列バインディング (like `DFX_Text`) に加えて、MFC がメモリ割り当てを制御し、正しい長さのアドレスを指定できるように、コールバックバインドが使用されます。 これは、MFC が常にデータを格納するように DAO "where" に指示して、メンバー変数に直接バインドできることを意味します。 バインド構造の残りの部分には、メモリ割り当てのコールバック関数のアドレスや、列のバインドの型 (列名によるバインド) などの情報が格納されます。

- `BindParam`

   これは、パラメーターメンバーに指定`SetParamValue`されたパラメーター値を使用してを呼び出す単純な操作です。

- `Fixup`

   各フィールドの**NULL**状態を入力します。

- `SetFieldNull`

   この操作では、各フィールドの状態を**NULL**としてマークするだけで、メンバー変数の値が**PSEUDO_NULL**に設定されます。

- `SetDirtyField`

   ダーティ`SetFieldValue`とマークされた各フィールドに対してを呼び出します。

残りのすべての操作では、データキャッシュの使用のみが処理されます。 データキャッシュは、特定の項目をより簡単にするために使用される、現在のレコード内のデータの余分なバッファーです。 たとえば、"ダーティ" フィールドは自動的に検出されます。 オンラインドキュメントで説明されているように、完全にまたはフィールドレベルでオフにすることができます。 バッファーの実装では、map を利用します。 このマップは、データの動的に割り当てられたコピーを "バインド" フィールド (または`CDaoRecordset`派生データメンバー) のアドレスと照合するために使用されます。

- `AllocCache`

   キャッシュされたフィールド値を動的に割り当てて、マップに追加します。

- `FreeCache`

   キャッシュされたフィールド値を削除し、マップから削除します。

- `StoreField`

   現在のフィールド値をデータキャッシュにコピーします。

- `LoadField`

   キャッシュされた値をフィールドメンバーにコピーします。

- `MarkForAddNew`

   現在のフィールド値が**NULL**でないかどうかを確認し、必要に応じてダーティとしてマークします。

- `MarkForEdit`

   現在のフィールド値とデータキャッシュを比較し、必要に応じてダーティとしてマークします。

> [!TIP]
> 標準データ型の既存の DFX ルーチンでカスタム DFX ルーチンをモデル化します。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
