---
title: 'テクニカル ノート 53: DAO データベース クラス用カスタム DFX ルーチン'
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
ms.openlocfilehash: f7ad854f4dbb4e90c09e886c69260e4e2eea3be2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365259"
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>テクニカル ノート 53: DAO データベース クラス用カスタム DFX ルーチン

> [!NOTE]
> DAO は Access データベースで使用され、Office 2013 を通じてサポートされます。 DAO 3.6 は最終バージョンであり、廃止と見なされます。 Visual C++ 環境およびウィザードは DAO をサポートしていません (ただし、DAO クラスは含まれていますが、使用することはできます)。 新しいプロジェクトには[、OLE DB テンプレート](../data/oledb/ole-db-templates.md)または[ODBC および MFC](../data/odbc/odbc-and-mfc.md)を使用することをお勧めします。 DAO は、既存のアプリケーションの保守にのみ使用してください。

このテクニカル ノートでは、DAO レコード フィールド エクスチェンジ (DFX) メカニズムについて説明します。 DFX ルーチンで何が起こっているかを理解するために、この`DFX_Text`関数を例として詳しく説明します。 このテクニカル ノートの追加の情報源として、他の個々の DFX 関数のコードを調べることができます。 カスタム RFX ルーチン (ODBC データベース クラスで使用される) が必要になる場合ほど、カスタム DFX ルーチンは必要ありません。

このテクニカル ノートには、次の内容が含まれています。

- DFX の概要

- DAO レコード フィールド エクスチェンジと動的バインディングの[使用例](#_mfcnotes_tn053_examples)

- [DFX の仕組み](#_mfcnotes_tn053_how_dfx_works)

- [カスタム DFX ルーチンの動作](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)

- [DFX_Textの詳細](#_mfcnotes_tn053_details_of_dfx_text)

**DFX の概要**

DAO レコード フィールド エクスチェンジ メカニズム (DFX) を使用すると、クラスを使用する場合の`CDaoRecordset`データの取得と更新の手順が簡略化されます。 クラスのデータ メンバーを使用してプロセスが`CDaoRecordset`簡略化されます。 から`CDaoRecordset`派生すると、テーブルまたはクエリの各フィールドを表すデータ メンバーを派生クラスに追加できます。 この「静的バインディング」メカニズムは単純ですが、すべてのアプリケーションで選択するデータフェッチ/更新方法ではない可能性があります。 DFX は、現在のレコードが変更されるたびに、すべての連結フィールドを取得します。 通貨が変更されたときにすべてのフィールドをフェッチする必要のないパフォーマンス重視のアプリケーションを開発する場合は、選択したデータ アクセス方法を`CDaoRecordset::GetFieldValue`介`CDaoRecordset::SetFieldValue`して「動的バインディング」を使用し、選択する可能性があります。

> [!NOTE]
> DFX と動的バインディングは相互に排他的ではないため、静的バインディングと動的バインディングのハイブリッド使用を使用できます。

## <a name="example-1--use-of-dao-record-field-exchange-only"></a><a name="_mfcnotes_tn053_examples"></a>例 1 - DAO レコード フィールド エクスチェンジのみの使用

(派生`CDaoRecordset`クラス`CMySet`が既に開かれていると仮定します)

```
// Add a new record to the customers table
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```

**例 2 — 動的バインディングのみの使用**

(クラスを`CDaoRecordset`使用していることを`rs`前提とし、既に開いています)

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

**例 3 - DAO レコード フィールド エクスチェンジと動的バインディングの使用**

(-derived クラス`emp`を使用`CDaoRecordset`して従業員データを参照することを想定しています)

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

## <a name="how-dfx-works"></a><a name="_mfcnotes_tn053_how_dfx_works"></a>DFX の仕組み

DFX メカニズムは、MFC ODBC クラスで使用されるレコード フィールド エクスチェンジ (RFX) 機構と同様の方法で動作します。 DFX と RFX の原理は同じですが、内部に多くの違いがあります。 DFX 関数の設計は、ほぼすべてのコードが個々の DFX ルーチンで共有されるようなものでした。 最高レベルの DFX では、いくつかの処理しか行いません。

- DFX は、必要に応じて SQL **SELECT**句および SQL**パラメータ**句を作成します。

- DFX は、DAO 関数で使用されるバインディング`GetRows`構造を構築します (詳細については、後で説明します)。

- DFX はダーティ フィールドの検出に使用されるデータ バッファを管理します (ダブル バッファリングが使用されている場合)。

- DFX は **、NULL**および**DIRTY**状態の配列を管理し、更新時に必要に応じて値を設定します。

DFX メカニズムの中心にあるのは`CDaoRecordset`、派生クラスの関数`DoFieldExchange`です。 この関数は、適切な操作タイプの個々の DFX 関数への呼び出しをディスパッチします。 内部`DoFieldExchange`MFC 関数を呼び出す前に、操作の種類を設定します。 次の一覧は、さまざまな操作の種類と簡単な説明を示しています。

|Operation|説明|
|---------------|-----------------|
|`AddToParameterList`|ビルド パラメーター句|
|`AddToSelectList`|SELECT 句を作成します。|
|`BindField`|バインド構造を設定します|
|`BindParam`|パラメータ値を設定します|
|`Fixup`|NULL ステータスを設定します|
|`AllocCache`|ダーティ チェック用にキャッシュを割り当てます。|
|`StoreField`|現在のレコードをキャッシュに保存します。|
|`LoadField`|キャッシュをメンバー値に復元します。|
|`FreeCache`|キャッシュを解放します|
|`SetFieldNull`|フィールドステータス&値を NULL に設定します。|
|`MarkForAddNew`|疑似 NULL でない場合はフィールドがダーティのマークを付けます|
|`MarkForEdit`|キャッシュに一致しない場合はフィールドがダーティのマークを付けます|
|`SetDirtyField`|ダーティとしてマークされたフィールド値を設定します|

次のセクションでは、各操作について詳しく説明します`DFX_Text`。

DAO レコード フィールドの交換プロセスについて理解する最も重要な機能は、`GetRows`オブジェクトの機能`CDaoRecordset`を使用することです。 DAO`GetRows`関数は、いくつかの方法で動作します。 このテクニカル ノートは、このテクニカル`GetRows`ノートの範囲外であるため、簡単に説明します。
DAO`GetRows`は、いくつかの方法で動作できます。

- 複数のレコードと複数のデータフィールドを一度に取得できます。 これにより、大規模なデータ構造を扱う複雑な複雑さと、各フィールドおよび構造内のデータの各レコードに対する適切なオフセットを扱う、より高速なデータアクセスが可能になります。 MFC では、この複数レコードフェッチメカニズムを利用しません。

- 別の`GetRows`方法として、プログラマは、1 つのデータ レコードに対して、各フィールドの取得されたデータのバインディング アドレスを指定できます。

- DAO は、呼び出し元がメモリを割り当てることができるように、可変長列の呼び出し元に "コールバック" も行います。 この 2 つ目の機能には、データのコピー数を最小限に抑えるだけでなく、クラス (派生クラス) のメンバー`CDaoRecordset`にデータを直接格納できるようにするという利点があります。 この 2 つ目の機構は、MFC が派生`CDaoRecordset`クラスのデータ メンバーにバインドするために使用するメソッドです。

## <a name="what-your-custom-dfx-routine-does"></a><a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a>カスタム DFX ルーチンの動作

この説明から、DFX 関数で実装される最も重要な操作は、 を正常に呼び出`GetRows`すために必要なデータ構造を設定する機能であることが明らかです。 DFX 関数がサポートする必要がある操作は他にも数多くありますが、`GetRows`呼び出しの準備を正しく行うほど重要なものも複雑なものもありません。

DFX の使用については、オンライン ドキュメントで説明します。 基本的に、2 つの要件があります。 まず、バインドされた各フィールドとパラメーター`CDaoRecordset`の派生クラスにメンバーを追加する必要があります。 これに続`CDaoRecordset::DoFieldExchange`いて、上書きする必要があります。 メンバのデータ型が重要であることに注意してください。 データベースのフィールドのデータと一致するか、少なくともその型に変換可能である必要があります。 たとえば、長整数などのデータベースの数値フィールドは、常にテキストに変換して`CString`メンバーにバインドできますが、データベース内のテキスト フィールドは、long 整数などの数値表現に変換され、長整数のメンバーにバインドされるとは限りません。 DAO と Jet データベース エンジンは、MFC ではなく変換を行います。

## <a name="details-of-dfx_text"></a><a name="_mfcnotes_tn053_details_of_dfx_text"></a>DFX_Textの詳細

前述のように、DFX の動作を説明する最善の方法は、例を通じて作業することです。 この目的のために内部を通過する`DFX_Text`は、DFXの少なくとも基本的な理解を提供するために非常にうまく動作するはずです。

- `AddToParameterList`

   この操作は、Jet**PARAMETERS**で必要な`Parameters <param name>, <param type> ... ;`SQL PARAMETERS 句 ("" を作成) を作成します。 各パラメータは、RFX 呼び出しで指定された名前と型付けされます。 個々の型`CDaoFieldExchange::AppendParamType`の名前を参照するには、関数関数を参照してください。 の場合`DFX_Text`、使用される型は**text**です。

- `AddToSelectList`

   SQL **SELECT**句を作成します。 DFX コールで指定された列名が単に追加される(")`SELECT <column name>, ...`と言えば、これはかなり簡単です。

- `BindField`

   操作の中で最も複雑です。 前述のように、ここで使用される DAO バインディング構造`GetRows`がセットアップされます。 構造体の情報の種類`DFX_Text`のコードからわかるように、使用される DAO 型 (**DAO_CHAR**または の場合**はDAO_WCHAR**`DFX_Text`が含まれます。 また、使用されるバインドの種類も設定されます。 前のセクション`GetRows`では簡単に説明しましたが、MFC で使用されるバインディングの種類は常に直接アドレス バインディング (**DAOBINDING_DIRECT**) であることを説明するだけで十分でした。 MFC がメモリ割り当てを制御し`DFX_Text`、正しい長さのアドレスを指定できるように、可変長列のバインド (など) のコールバック バインディングが使用されます。 つまり、MFC は常に DAO にデータを配置する場所を指定できるため、メンバー変数に直接バインドできます。 バインディング構造体の残りの部分は、メモリ割り当てコールバック関数のアドレスや列のバインドの型 (列名によるバインド) などで埋められます。

- `BindParam`

   これは、パラメーター メンバーで指定`SetParamValue`されたパラメーター値を使用して呼び出す単純な操作です。

- `Fixup`

   各フィールドの**NULL**ステータスを入力します。

- `SetFieldNull`

   この操作では、各フィールドの状態を**NULL**としてマークし、メンバー変数の値を**PSEUDO_NULL**に設定します。

- `SetDirtyField`

   ダー`SetFieldValue`ティとマークされた各フィールドの呼び出し。

残りのすべての操作は、データ キャッシュの使用のみを処理します。 データ キャッシュは、特定のデータを簡単にするために使用される現在のレコードのデータの追加バッファーです。 たとえば、「ダーティ」フィールドは自動的に検出されます。 オンラインドキュメントで説明されているように、完全にオフにすることも、フィールドレベルでオフにすることもできます。 バッファの実装では、マップを利用します。 このマップは、データの動的に割り当てられたコピーを"バインドされた"フィールド(または`CDaoRecordset`派生データ メンバー)のアドレスと照合するために使用されます。

- `AllocCache`

   キャッシュされたフィールド値を動的に割り当て、マップに追加します。

- `FreeCache`

   キャッシュされたフィールド値を削除し、マップから削除します。

- `StoreField`

   現在のフィールド値をデータ キャッシュにコピーします。

- `LoadField`

   キャッシュされた値をフィールド メンバーにコピーします。

- `MarkForAddNew`

   現在のフィールド値が**NULL**以外であるかどうかをチェックし、必要に応じてダーティマークを付けます。

- `MarkForEdit`

   現在のフィールド値をデータ キャッシュと比較し、必要に応じてダーティマークを付けます。

> [!TIP]
> 標準データ型の既存の DFX ルーチンでカスタム DFX ルーチンをモデル化します。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
