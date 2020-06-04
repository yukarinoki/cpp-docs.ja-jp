---
title: CDaoFieldInfo 構造体
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
ms.openlocfilehash: 9466386fefc6e5ab8fcf89bf497c1d5219e3e807
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368410"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo 構造体

この`CDaoFieldInfo`構造体には、データ アクセス オブジェクト (DAO) に定義されたフィールド オブジェクトに関する情報が含まれています。

DAO は Office 2013 を通じてサポートされています。 DAO 3.6 は最終バージョンであり、廃止と見なされます。

## <a name="syntax"></a>構文

```
struct CDaoFieldInfo
{
    CString m_strName;           // Primary
    short m_nType;               // Primary
    long m_lSize;                // Primary
    long m_lAttributes;          // Primary
    short m_nOrdinalPosition;    // Secondary
    BOOL m_bRequired;            // Secondary
    BOOL m_bAllowZeroLength;     // Secondary
    long m_lCollatingOrder;      // Secondary
    CString m_strForeignName;    // Secondary
    CString m_strSourceField;    // Secondary
    CString m_strSourceTable;    // Secondary
    CString m_strValidationRule; // All
    CString m_strValidationText; // All
    CString m_strDefaultValue;   // All
};
```

#### <a name="parameters"></a>パラメーター

*m_strName*<br/>
フィールド オブジェクトに一意の名前を付けます。 詳細については、DAO ヘルプの「プロパティ名」を参照してください。

*m_nType*<br/>
フィールドのデータ型を示す値。 詳細については、DAO ヘルプの「型プロパティ」を参照してください。 このプロパティの値は、次のいずれかになります。

- `dbBoolean`はい/いいえ、TRUE/FALSE と同じです。

- `dbByte`バイト

- `dbInteger`短い

- `dbLong`長い

- `dbCurrency`通貨;MFC クラス[を参照してください。](../../mfc/reference/colecurrency-class.md)

- `dbSingle`単一

- `dbDouble`ダブル

- `dbDate`日付/時刻;MFC クラス[を参照してください。](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText`テキスト。MFC クラス[CString を](../../atl-mfc-shared/reference/cstringt-class.md)参照してください。

- `dbLongBinary`Long Binary (OLE オブジェクト); クラス`CLongBinary`の代わりに MFC クラス [CByteArray](../../mfc/reference/cbytearray-class.md) を使用して、`CByteArray`より豊富で使いやすいものにすることができます。

- `dbMemo`メモ;MFC クラスを参照してください。`CString`

- `dbGUID`リモート プロシージャ 呼び出しで使用されるグローバル一意識別子/ユニバーサル一意識別子。 詳細については、DAO ヘルプの「型プロパティ」を参照してください。

> [!NOTE]
> バイナリ データには文字列データ型を使用しないでください。 これにより、データが Unicode/ANSI 変換レイヤを通過し、オーバーヘッドが増加し、予期しない変換が発生する可能性があります。

*m_lSize*<br/>
テキストまたは数値を含むフィールド オブジェクトの固定サイズを含む DAO フィールド オブジェクトの最大サイズ (バイト単位) を示す値。 詳細については、DAO ヘルプの「プロパティのサイズ」を参照してください。 サイズは、次のいずれかの値になります。

|Type|サイズ (バイト)|説明|
|----------|--------------------|-----------------|
|`dbBoolean`|1 バイト|はい/いいえ (真/偽と同じ)|
|`dbByte`|1|Byte|
|`dbInteger`|2|Integer|
|`dbLong`|4|Long|
|`dbCurrency`|8|通貨 ([コレ通貨](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Single|
|`dbDouble`|8|Double|
|`dbDate`|8|日付/時刻 ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|テキスト ([C文字列](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|長いバイナリ (OLE オブジェクト;[バイト配列](../../mfc/reference/cbytearray-class.md);`CLongBinary`の代わりに使用する)|
|`dbMemo`|0|メモ ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|リモート プロシージャ 呼び出しで使用されるグローバル一意識別子/ユニバーサル一意識別子。|

*m_lAttributes*<br/>
テーブル定義、レコードセット、クエリ定義、またはインデックス オブジェクトに含まれるフィールド オブジェクトの特性を指定します。 返される値は、C++ ビットごとの OR (**&#124;**) 演算子を使用して作成された、これらの定数の合計です。

- `dbFixedField`フィールドサイズは固定です (数値フィールドの場合はデフォルト)。

- `dbVariableField`フィールドサイズは可変です (テキストフィールドのみ)。

- `dbAutoIncrField`新しいレコードのフィールド値は、変更できない一意の長整数に自動的にインクリメントされます。 Jet データベース テーブルでのみサポートされます。

- `dbUpdatableField`フィールド値は変更できます。

- `dbDescending`フィールドは降順 (Z - A または 100 - 0) の順序で並べ替えられます (インデックス オブジェクトの Fields コレクション内のフィールド オブジェクトにのみ適用され、MFC ではインデックス オブジェクト自体がテーブル定義オブジェクトに含まれます)。 この定数を省略すると、フィールドは昇順 (A - Z または 0 - 100) で並べ替えられます (デフォルト)。

このプロパティの設定を確認する場合、C++ ビットごとの AND 演算子 (**&**) を使用して、特定の属性をテストできます。 複数の属性を設定する場合、適切な定数とビットごとの OR (**&#124;**) 演算子を組み合わせて結合できます。 詳細については、DAO ヘルプの「属性プロパティ」を参照してください。

*m_nOrdinalPosition*<br/>
DAO フィールド オブジェクトで表されるフィールドを他のフィールドとの相対位置で表示する順序を指定する値。 このプロパティは[、次のように設定](../../mfc/reference/cdaotabledef-class.md#createfield)できます。 詳細については、DAO ヘルプのトピック「OrdinalPosition プロパティ」を参照してください。

*m_bRequired*<br/>
DAO フィールド オブジェクトに Null 以外の値が必要かどうかを示します。 このプロパティが TRUE の場合、フィールドは Null 値を許可しません。 必須が FALSE に設定されている場合、フィールドには Null 値だけでなく、"AllowZeroLength/入力規則のプロパティ設定" で指定された条件を満たす値を含めることができます。 詳細については、DAO ヘルプの「必須プロパティ」を参照してください。 このプロパティは、テーブル定義に対[して設定](../../mfc/reference/cdaotabledef-class.md#createfield)できます。

*m_bAllowZeroLength*<br/>
空の文字列 ("") が、テキスト型またはメモ型の DAO フィールド オブジェクトの有効な値であるかどうかを示します。 このプロパティが TRUE の場合、空の文字列は有効な値です。 このプロパティを FALSE に設定すると、空の文字列を使用してフィールドの値を設定することができなくなります。 詳細については、DAO ヘルプのトピック「長さのプロパティを許可する」を参照してください。 このプロパティは、テーブル定義に対[して設定](../../mfc/reference/cdaotabledef-class.md#createfield)できます。

*m_lCollatingOrder*<br/>
文字列の比較または並べ替えのための文字列の並べ替え順序を指定します。 詳細については、DAO ヘルプの「データ アクセス用の Windows レジストリ設定のカスタマイズ」を参照してください。 返される値の一覧については、`m_lCollatingOrder`[構造体](../../mfc/reference/cdaodatabaseinfo-structure.md)のメンバーを参照してください。 このプロパティは、テーブル定義に対[して設定](../../mfc/reference/cdaotabledef-class.md#createfield)できます。

*m_strForeignName*<br/>
リレーションシップ内の値で、プライマリ テーブルのフィールドに対応する外部テーブルの DAO フィールド オブジェクトの名前を指定します。 詳細については、DAO ヘルプの「外部名プロパティ」を参照してください。

*m_strSourceField*<br/>
テーブル定義、レコードセット、またはクエリ定義オブジェクトに含まれる DAO フィールド オブジェクトのデータの元のソースであるフィールドの名前を示します。 このプロパティは、フィールド オブジェクトに関連付けられている元のフィールド名を示します。 たとえば、このプロパティを使用して、基になるテーブルのフィールドの名前とは無関係の名前を持つクエリ フィールドのデータの元のソースを確認できます。 詳細については、DAO ヘルプのトピック「ソースフィールド、ソーステーブルのプロパティ」を参照してください。 このプロパティは、テーブル定義に対[して設定](../../mfc/reference/cdaotabledef-class.md#createfield)できます。

*m_strSourceTable*<br/>
テーブル定義、レコードセット、またはクエリ定義オブジェクトに含まれる DAO フィールド オブジェクトのデータの元のソースであるテーブルの名前を示します。 このプロパティは、フィールド オブジェクトに関連付けられている元のテーブル名を示します。 たとえば、このプロパティを使用して、基になるテーブルのフィールドの名前とは無関係の名前を持つクエリ フィールドのデータの元のソースを確認できます。 詳細については、DAO ヘルプのトピック「ソースフィールド、ソーステーブルのプロパティ」を参照してください。 このプロパティは、テーブル定義に対[して設定](../../mfc/reference/cdaotabledef-class.md#createfield)できます。

*m_strValidationRule*<br/>
フィールドのデータが変更またはテーブルに追加される場合に、そのデータを検証する値。 詳細については、DAO ヘルプの「検証ルールプロパティ」を参照してください。 このプロパティは、テーブル定義に対[して設定](../../mfc/reference/cdaotabledef-class.md#createfield)できます。

テーブル定義の関連情報については、構造体の`m_strValidationRule`メンバー[を](../../mfc/reference/cdaotabledefinfo-structure.md)参照してください。

*m_strValidationText*<br/>
DAO フィールド オブジェクトの値が、ValidationRule プロパティ設定で指定された入力規則を満たしていない場合に、アプリケーションが表示するメッセージのテキストを指定する値。 詳細については、DAO ヘルプの「検証テキスト プロパティ」を参照してください。 このプロパティは、テーブル定義に対[して設定](../../mfc/reference/cdaotabledef-class.md#createfield)できます。

*m_strDefaultValue*<br/>
DAO フィールド オブジェクトの既定値。 新しいレコードが作成されると、DefaultValue プロパティの設定がフィールドの値として自動的に入力されます。 詳細については、DAO ヘルプの「既定値のプロパティ」を参照してください。 このプロパティは、テーブル定義に対[して設定](../../mfc/reference/cdaotabledef-class.md#createfield)できます。

## <a name="remarks"></a>解説

上記のプライマリ、セカンダリ、およびすべてへの参照は、[クラス CDaoTableDef 、CDaoQueryDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)、および[CDaoRecordset](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)の`GetFieldInfo`メンバー関数によって情報がどのように返されるかを示[します](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)。

フィールド オブジェクトは MFC クラスでは表されません。 代わりに、次のクラスの MFC オブジェクトの基になる DAO オブジェクトには[、フィールド](../../mfc/reference/cdaotabledef-class.md)オブジェクトの[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)コレクションが含[まれています。](../../mfc/reference/cdaoquerydef-class.md) これらのクラスは、フィールド情報の個々の項目にアクセスするためのメンバー関数を提供するか、または、オブジェクトを含`CDaoFieldInfo`むオブジェクトのメンバー`GetFieldInfo`関数を呼び出すことによって、それらを一度にすべてアクセスできます。

オブジェクトプロパティの検査に使用する以外`CDaoFieldInfo`に、tabledef で新しいフィールドを作成するための入力パラメータを作成することもできます。 このタスクでは、より簡単なオプションを使用できますが、より細かいコントロールが必要な場合は、パラメーターを受け取る[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)のバージョンを`CDaoFieldInfo`使用できます。

メンバー関数 (フィールド`GetFieldInfo`を含むクラス) によって取得された情報は、構造体に`CDaoFieldInfo`格納されます。 Fields`GetFieldInfo`コレクションのフィールド オブジェクトが格納されている、格納しているオブジェクトのメンバー関数を呼び出します。 `CDaoFieldInfo`また、デバッグ`Dump`ビルドでメンバー関数を定義します。 を使用`Dump`して、オブジェクトの内容を`CDaoFieldInfo`ダンプできます。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[次の項目を取得します。](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[コダレコード::ゲットフィールドインフォ](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)
