---
title: 'TN053: DAO 用カスタム DFX ルーチン データベース クラス |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.dfx
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60e42aedd406e7478db83ecddca7d8b82230abc5
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951995"
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>テクニカル ノート 53: DAO データベース クラス用カスタム DFX ルーチン
> [!NOTE]
>  Visual C 環境とウィザードは、(ただし、DAO クラスが含まれると、引き続き使用することができます) DAO をサポートしています。 使用することをお勧めします。 [OLE DB テンプレート](../data/oledb/ole-db-templates.md)または[ODBC と MFC](../data/odbc/odbc-and-mfc.md)新しいプロジェクトのです。 DAO は、既存のアプリケーションを保守でのみ使用する必要があります。  
  
 このテクニカル ノートでは、DAO レコード フィールド エクス (チェンジ DFX) メカニズムについて説明します。 DFX ルーチンで何が起こっているかの理解に役立つ、`DFX_Text`関数は、例として詳細で説明します。 このテクニカル ノートの情報の追加のソースとしてコードを調べて、一方が他方の個々 の DFX 関数。 おそらく必要はありませんカスタム DFX ルーチン必要に応じてカスタム RFX ルーチン (ODBC データベース クラスで使用) する必要があります。  
  
 このテクニカル ノートが含まれています。  
  
-   DFX の概要  
  
- [例](#_mfcnotes_tn053_examples)DAO レコード フィールド エクス チェンジと動的なバインドを使用します。  
  
- [DFX のしくみ](#_mfcnotes_tn053_how_dfx_works)  
  
- [カスタム DFX ルーチンの実行内容](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)  
  
- [DFX_Text の詳細](#_mfcnotes_tn053_details_of_dfx_text)  
  
 **DFX の概要**  
  
 DAO レコード フィールド エクス機構 (エクス チェンジ DFX) を使用して、取得して、データの更新を使用する場合の手順を簡素、`CDaoRecordset`クラスです。 データ メンバーを使用して、プロセスが簡素化、`CDaoRecordset`クラスです。 派生することによって`CDaoRecordset`、テーブルまたはクエリ内の各フィールドを表す、派生クラスにデータ メンバーを追加することができます。 この「静的バインド」機構は単純な場合がすべてのアプリケーションの任意のデータのフェッチまたは更新方法ができない可能性があります。 DFX は、現在のレコードが変更されるたびにすべてのバインドされたフィールドを取得します。 通貨が変更されたときに、すべてのフィールドをフェッチが不要なパフォーマンス重視のアプリケーションを開発している場合「動的バインド」を使用して`CDaoRecordset::GetFieldValue`と`CDaoRecordset::SetFieldValue`任意のデータ アクセス方法があります。  
  
> [!NOTE]
>  DFX と動的バインドされない相互に排他的な静的および動的なバインドのハイブリッドの使用を使用できるようにします。  
  
## <a name="_mfcnotes_tn053_examples"></a> DAO レコード フィールド エクス チェンジのみの使用例 1:  
  
 (想定`CDaoRecordset`: 派生クラス`CMySet`既に開かれている)  
  
```  
// Add a new record to the customers table  
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```  
  
 **動的バインドのみの使用例 2:**  
  
 (を使用すると仮定`CDaoRecordset`クラス、`rs`が既に開かれている)  
  
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
  
 **例 3-使用の DAO レコード フィールド エクス チェンジと動的な連結**  
  
 (参照の従業員データを前提としています`CDaoRecordset`-派生クラス`emp`)  
  
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
  
## <a name="_mfcnotes_tn053_how_dfx_works"></a> DFX のしくみ  
  
 DFX 機構は、同様に、レコード フィールド エクス (チェンジ RFX) メカニズムを使用して、MFC ODBC クラスに機能します。 DFX と RFX の原則は、同じが多数の内部的な相違があります。 DFX 関数の設計は、個々 の DFX ルーチンによってほとんどすべてのコードを共有するようでした。 最上位の DFX のみが、いくつか。  
  
-   DFX 構築 SQL**選択**句と SQL**パラメーター**必要な場合は、句。  
  
-   DFX は、DAO のによって使用されるバインディングの構造を構築`GetRows`関数 (詳細は後述)。  
  
-   DFX (ダブル バッファリングが使用されている) 場合は、ダーティであるフィールドを検出するために使用するデータ バッファーを管理します。  
  
-   DFX は、管理、 **NULL**と**DIRTY**ステータスが配列や、更新プログラムに必要な場合に値を設定します。  
  
 メカニズムは、DFX の中核、`CDaoRecordset`派生クラスの`DoFieldExchange`関数。 この関数は、適切な操作の種類の個々 の DFX 関数への呼び出しをディスパッチします。 呼び出しの前に`DoFieldExchange`内部 MFC 関数は、操作の種類を設定します。 さまざまな操作の種類と簡単な説明を次に示します。  
  
|操作|説明|  
|---------------|-----------------|  
|`AddToParameterList`|ビルド パラメーター句|  
|`AddToSelectList`|ビルドの SELECT 句|  
|`BindField`|バインド構造体を設定します。|  
|`BindParam`|パラメーター値を設定します。|  
|`Fixup`|NULL の状態を設定します。|  
|`AllocCache`|ダーティ チェックのキャッシュを割り当てます|  
|`StoreField`|現在のレコードをキャッシュに保存します。|  
|`LoadField`|メンバー値に復元キャッシュ|  
|`FreeCache`|キャッシュを解放します。|  
|`SetFieldNull`|フィールドの状態と値を NULL に設定|  
|`MarkForAddNew`|記号フィールドがダーティかどう擬似 NULL|  
|`MarkForEdit`|記号フィールド ダーティの場合はキャッシュに一致しません。|  
|`SetDirtyField`|フィールド ダーティとマークされている値の設定|  
  
 次のセクションで各操作については説明のさらに詳しく`DFX_Text`です。  
  
 DAO レコード フィールドの交換プロセスについて理解して最も重要な機能を使用している、`GetRows`の関数、`CDaoRecordset`オブジェクト。 DAO`GetRows`関数がいくつかの方法で作業できます。 このテクニカル ノートは簡単に説明が`GetRows`このテクニカル ノートのスコープ外であるためです。  
  
 DAO`GetRows`いくつかの方法で作業できます。  
  
-   複数のレコードと複数のデータ フィールドを一度に取得できます。 これにより、大規模なデータ構造、および各フィールドに適切なオフセットを処理する場合の複雑な高速データ アクセスの構造内のデータのレコードごとにできます。 MFC には、複数レコードのフェッチ機構の利点は取りません。  
  
-   別の方法`GetRows`できる作業は、プログラマ、各フィールドのデータの 1 つのレコードの取得したデータのバインド アドレスを指定するために使用できるようにします。  
  
-   DAO も""を呼び出して、呼び出し元の可変長列のメモリを割り当て、呼び出し元を許可するためにします。 この 2 つ目の機能には、データのコピーの数を最小限に抑えるだけでなく、クラスのメンバーへのデータの格納を許可の利点は、(、`CDaoRecordset`派生クラス)。 この 2 番目のメカニズムは、MFC で使用するデータ メンバーにバインドする方法を`CDaoRecordset`クラスを派生します。  
  
##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a> カスタム DFX ルーチンの実行内容  
 DFX 関数で実装される最も重要な操作が正常に呼び出すに必要なデータ構造を設定する機能をする必要があるの説明からは`GetRows`します。 DFX 関数が同様に、サポートが必要なその他の操作が、重要なまたは正しく準備として複合型として none の数が、`GetRows`呼び出します。  
  
 DFX の使用は、オンライン ドキュメントの説明です。 基本的には、2 つの要件があります。 最初に、メンバーを追加する必要があります、`CDaoRecordset`の各バインドされたフィールドとパラメーター クラスを派生します。 次のこの`CDaoRecordset::DoFieldExchange`オーバーライドする必要があります。 メンバーのデータ型は、重要なことに注意してください。 データベース内のフィールドからのデータと一致する必要があります、その型に変換できる型には、少なくともまたはことができます。 たとえば long 整数などのデータベース内の数値フィールドは常にテキストに変換されにバインドされている、`CString`メンバーがデータベース内のテキスト フィールドが必ずしも長整数型などの数値表現に変換され長い integ にバインドされています。er メンバー。 DAO および Microsoft Jet データベース エンジンは、変換 (なく MFC) を行います。  
  
##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a> DFX_Text の詳細  
 前述のように、DFX のしくみを説明する最善の方法、サンプルを使って作業を開始します。 このための内部を通過`DFX_Text`少なくとも DFX の基本的な知識を提供するのに役立つうまく動作する必要があります。  
  
 `AddToParameterList`  
 この操作は、SQL をビルド**パラメーター**句 ("`Parameters <param name>, <param type> ... ;`") Jet で必要です。 各パラメーターがという名前し、rfx 関数の呼び出しで指定) (として型指定します。 関数を参照してください`CDaoFieldExchange::AppendParamType`個別の型の名前を表示する関数。 場合、 `DFX_Text`、使用された型は**テキスト**です。  
  
 `AddToSelectList`  
 SQL をビルド**選択**句。 とても簡単 DFX 呼び出しによって指定された列名が単に付加 ("`SELECT <column name>, ...`") です。  
  
 `BindField`  
 最も複雑な操作です。 既に説明したように、これは DAO バインド構造体がによってどのように使用されている`GetRows`を設定します。 内のコードからわかるように`DFX_Text`構造内の情報の種類には、DAO の型が含まれます (**DAO_CHAR**または**DAO_WCHAR**の場合、 `DFX_Text`)。 さらに、使用されるバインディングの種類も設定します。 前のセクションで`GetRows`ごく短時間しか」で説明したが、MFC によって使用されるバインドの種類は、直接アドレスのバインドでは常に説明するための十分な (**DAOBINDING_DIRECT**)。 さらに可変長列のバインドの (と同様に`DFX_Text`) MFC をメモリ割り当てを制御し、正しい長さのアドレスを指定するためのコールバックのバインディングが使用されます。 つまり、MFC を常に把握 DAO メンバー変数に直接バインドできるように、データを格納する"where"です。 メモリ割り当てのコールバック関数と、(列の名前でバインド) 列のバインドの種類のアドレスなど、バインド構造体の残りの部分が入力されます。  
  
 `BindParam`  
 これは、単純な操作を呼び出す`SetParamValue`メンバーのパラメーターで指定されたパラメーターの値。  
  
 `Fixup`  
 入力、 **NULL**各フィールドの状態。  
  
 `SetFieldNull`  
 この操作を各フィールドの状態としてマークするだけ**NULL**メンバー変数の値を設定および**PSEUDO_** です。  
  
 `SetDirtyField`  
 呼び出し`SetFieldValue`各フィールドをダーティとマークします。  
  
 残りのすべての操作のみ、データ キャッシュを使用してを処理します。 データ キャッシュは、一定の処理を簡単に使用される現在のレコード内のデータの余分なバッファーです。 たとえば、「ダーティ」フィールドを自動的に検出することができます。 オンライン ドキュメントの説明に従って完全にまたは、フィールド レベルで無効にできます。 バッファーの実装は、マップを利用しています。 このマップは、動的に割り当てられたデータのコピー「バインド」フィールドのアドレスを照合に使用されます (または`CDaoRecordset`データ メンバーの派生)。  
  
 `AllocCache`  
 動的なキャッシュされたフィールドの値の割り当てし、マップに追加します。  
  
 `FreeCache`  
 キャッシュされたフィールドの値を削除し、マップから削除します。  
  
 `StoreField`  
 データ キャッシュに現在のフィールドの値をコピーします。  
  
 `LoadField`  
 フィールドのメンバーに、キャッシュされた値をコピーします。  
  
 `MarkForAddNew`  
 現在のフィールド値が非チェック**NULL**し、必要に応じてダーティ マークします。  
  
 `MarkForEdit`  
 データ キャッシュを使用して現在のフィールドの値を比較し、必要な場合は、ダーティのマークを付けます。  
  
> [!TIP]
>  標準のデータ型の既存の DFX ルーチン、用カスタム DFX ルーチン モデルです。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

