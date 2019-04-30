---
title: CDaoFieldInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CDaoFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
ms.openlocfilehash: a5c4013a323c85ad19a3fade20f76852e053362a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399825"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo 構造体

`CDaoFieldInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているフィールド オブジェクトに関する情報が含まれています。

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
フィールド オブジェクトの一意名します。 詳細については、「Name プロパティ」DAO ヘルプのトピックを参照してください。

*m_nType*<br/>
フィールドのデータ型を示す値。 詳細については、「型のプロパティ」DAO ヘルプのトピックを参照してください。 このプロパティの値には、次のいずれかを指定できます。

- `dbBoolean` はい/いいえ、TRUE または FALSE と同じ

- `dbByte` バイト

- `dbInteger` 短い

- `dbLong` 長い

- `dbCurrency` 通貨です。MFC クラスを参照してください[COleCurrency](../../mfc/reference/colecurrency-class.md)

- `dbSingle` 1 つ

- `dbDouble` Double 型

- `dbDate` 日付/時刻です。MFC クラスを参照してください[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText` テキスト。MFC クラスを参照してください[CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary` 長いバイナリ (オブジェクト)MFC クラスを使用したい場合があります[CByteArray](../../mfc/reference/cbytearray-class.md)クラスではなく`CLongBinary`として`CByteArray`は高度なと簡単に使用します。

- `dbMemo` メモします。MFC クラスを参照してください `CString`

- `dbGUID` グローバルに一意の識別子/汎用一意の識別子リモート プロシージャ コールで使用されます。 詳細については、「型のプロパティ」DAO ヘルプのトピックを参照してください。

> [!NOTE]
>  バイナリ データの文字列データ型を使用しないでください。 これにより、オーバーヘッドが増加し、予期しない変換結果として、UNICODE/ANSI 変換レイヤーを通過するデータ。

*m_lSize*<br/>
テキストまたはテキストまたは数値の値を含むフィールド オブジェクトの固定サイズを含む、DAO フィールド オブジェクトのバイト単位の最大サイズを示す値。 詳細については、「Size プロパティ」DAO ヘルプのトピックを参照してください。 サイズには、次の値のいずれかを指定できます。

|型|サイズ (バイト)|説明|
|----------|--------------------|-----------------|
|`dbBoolean`|1 バイト|はい/いいえ (True または False と同じ)|
|`dbByte`|1|Byte|
|`dbInteger`|2|整数型|
|`dbLong`|4|Long|
|`dbCurrency`|8|通貨 ([COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Single|
|`dbDouble`|8|倍精度浮動小数点型|
|`dbDate`|8|日付/時刻 ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|テキスト ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|長いバイナリ (OLE オブジェクト。[CByteArray](../../mfc/reference/cbytearray-class.md); の代わりに使用`CLongBinary`)|
|`dbMemo`|0|メモ ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|グローバルに一意の識別子/汎用一意の識別子リモート プロシージャ コールで使用されます。|

*m_lAttributes*<br/>
テーブル定義、レコード セット、クエリ定義、またはインデックスのオブジェクトに含まれるフィールド オブジェクトの特性を指定します。 返される値はビットごとの OR、C++ で作成されたこれらの定数の合計を指定できます (**&#124;**) 演算子。

- `dbFixedField` フィールド サイズが (数値フィールドの既定値) を修正しました。

- `dbVariableField` フィールド サイズは、変数 (テキスト フィールドのみ) です。

- `dbAutoIncrField` 新しいレコードのフィールドの値は、変更できない一意の long 整数を自動的にインクリメントされます。 Microsoft Jet データベースのテーブルに対してのみサポートされます。

- `dbUpdatableField` フィールドの値を変更できます。

- `dbDescending` 降順で並べ替えられます (Z、A または 100-0) 順序 (インデックス オブジェクトのフィールド コレクションでは、mfc では、オブジェクト自体に含まれるテーブル定義のオブジェクトのインデックスのフィールド オブジェクトにのみ適用されます)。 この定数を省略した場合に昇順に並べ替えられます (A ~ Z、0 - 100) 順序 (既定値)。

このプロパティの設定をチェックするときに使用できます、C++ ビット処理、および演算子 (**&**) 特定の属性をテストします。 ビットごとの OR と適切な定数を組み合わせることで組み合わせることができますに複数の属性を設定するとき (**&#124;**) 演算子。 詳細については、「属性のプロパティ」DAO ヘルプのトピックを参照してください。

*m_nOrdinalPosition*<br/>
その他のフィールドとして表示される、DAO フィールド オブジェクトによって表されるフィールドをする数値の順序を指定する値。 このプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。 詳細については、「OrdinalPosition プロパティ」DAO ヘルプのトピックを参照してください。

*m_bRequired*<br/>
DAO field オブジェクトに Null 以外の値が必要かどうかを示します。 このプロパティが TRUE の場合、フィールドは Null 値を許可しません。 FALSE に設定されているために必要な場合、フィールドは、Null 値と AllowZeroLength および ValidationRule プロパティの設定で指定された条件を満たす値に含めることができます。 詳細については、「DAO のヘルプ「プロパティのために必要な」」を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。

*m_bAllowZeroLength*<br/>
示すかどうか、空の文字列 ("") データ型がテキストまたはメモの DAO フィールド オブジェクトの有効な値です。 このプロパティが TRUE の場合、空の文字列は、有効な値です。 このプロパティは、フィールドの値を設定する空の文字列を使用できないことを確認する場合は FALSE に設定できます。 詳細については、「AllowZeroLength プロパティ」DAO ヘルプのトピックを参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。

*m_lCollatingOrder*<br/>
文字列比較または並べ替え用のテキストの並べ替え順序を指定します。 詳細については、"をカスタマイズする Windows レジストリの設定に Data Access"DAO ヘルプのトピックを参照してください。 返される値の一覧を参照してください、`m_lCollatingOrder`のメンバー、 [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md)構造体。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。

*m_strForeignName*<br/>
リレーションシップ、主テーブル内のフィールドに対応する外部テーブル内の DAO フィールド オブジェクトの名前を指定する値。 詳細については、「ForeignName プロパティ」DAO ヘルプのトピックを参照してください。

*m_strSourceField*<br/>
テーブル定義、レコード セット、またはクエリ定義のオブジェクトに含まれる DAO フィールド オブジェクトのデータの元のソースであるフィールドの名前を示します。 このプロパティは、フィールド オブジェクトに関連付けられている元のフィールド名を示します。 たとえば、基になるテーブルのフィールドの名前に関連する名前のないクエリ フィールドのデータの元のソースを判断するのにこのプロパティを使用できます。 詳細については、DAO のヘルプ トピック"SourceField SourceTable プロパティ"を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。

*m_strSourceTable*<br/>
テーブル定義、レコード セット、またはクエリ定義のオブジェクトに含まれる DAO フィールド オブジェクトのデータの元のソースであるテーブルの名前を示します。 このプロパティは、フィールド オブジェクトに関連付けられている元のテーブル名を示します。 たとえば、基になるテーブルのフィールドの名前に関連する名前のないクエリ フィールドのデータの元のソースを判断するのにこのプロパティを使用できます。 詳細については、DAO のヘルプ トピック"SourceField SourceTable プロパティ"を参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。

*m_strValidationRule*<br/>
変更されたか、テーブルに追加するフィールドのデータを検証する値。 詳細については、"Validationrule"DAO ヘルプのトピックを参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。

テーブル定義の詳細については、次を参照してください。、`m_strValidationRule`のメンバー、 [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md)構造体。

*m_strValidationText*<br/>
DAO のフィールド オブジェクトの値が、ValidationRule プロパティの設定で指定された検証規則を満たしていない場合、アプリケーションで表示されるメッセージのテキストを指定する値。 詳細については、「プロパティ」DAO ヘルプのトピックを参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。

*m_strDefaultValue*<br/>
DAO フィールド オブジェクトの既定値。 新しいレコードが作成されたときに、DefaultValue プロパティの設定が自動的に入力値としてフィールド。 詳細については、「DefaultValue プロパティ」DAO ヘルプのトピックを参照してください。 テーブル定義でのこのプロパティを設定することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)します。

## <a name="remarks"></a>Remarks

プライマリ、セカンダリ、および上記のすべてへの参照情報がによって返される方法を示すため、`GetFieldInfo`クラスのメンバー関数[CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)、 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)、および[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)します。

オブジェクトのフィールドは、MFC クラスでは表されません。 代わりに、次のクラスの MFC オブジェクトを基になる DAO オブジェクトには、フィールド オブジェクトのコレクションが含まれます。[CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)、および[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)します。 これらのクラスのフィールドについては、各アイテムにアクセスするメンバー関数を指定するか、それらを一度にすべてにアクセスできます、`CDaoFieldInfo`オブジェクトを呼び出すことによって、`GetFieldInfo`親オブジェクトのメンバー関数。

オブジェクトのプロパティを確認するための用途以外使用することも`CDaoFieldInfo`テーブル定義に新しいフィールドを作成するための入力パラメーターを作成します。 単純なオプションはこのタスクで使用できますが、さらに細かく制御する場合は、バージョンを使用することができます[CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)を受け取る、`CDaoFieldInfo`パラメーター。

によって取得される情報、`GetFieldInfo`に (フィールドを含むクラス) のメンバー関数が格納されている、`CDaoFieldInfo`構造体。 呼び出す、 `GetFieldInfo` Fields コレクションを持つフィールド オブジェクトが格納されている親オブジェクトのメンバー関数。 `CDaoFieldInfo` 定義、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoFieldInfo`オブジェクト。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)
