---
description: '詳細については、次を参照してください: CDaoTableDefInfo 構造体'
title: CDaoTableDefInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CDaoTableDefInfo
helpviewer_keywords:
- CDaoTableDefInfo structure [MFC]
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
ms.openlocfilehash: 953a255b35860dcce0ac8d3ef5081951dd15c344
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247970"
---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo 構造体

構造体には、 `CDaoTableDefInfo` データアクセスオブジェクト (DAO) 用に定義されたテーブルオブジェクトオブジェクトに関する情報が含まれています。

## <a name="syntax"></a>構文

```
struct CDaoTableDefInfo
{
    CString m_strName;               // Primary
    BOOL m_bUpdatable;               // Primary
    long m_lAttributes;              // Primary
    COleDateTime m_dateCreated;      // Secondary
    COleDateTime m_dateLastUpdated;  // Secondary
    CString m_strSrcTableName;       // Secondary
    CString m_strConnect;            // Secondary
    CString m_strValidationRule;     // All
    CString m_strValidationText;     // All
    long m_lRecordCount;             // All
};
```

#### <a name="parameters"></a>パラメーター

*m_strName*<br/>
Tabledef オブジェクトに一意の名前を定義します。 このプロパティの値を直接取得するには、tabledef オブジェクトの [GetName](../../mfc/reference/cdaotabledef-class.md#getname) メンバー関数を呼び出します。 詳細については、DAO ヘルプの「Name プロパティ」を参照してください。

*m_bUpdatable*<br/>
テーブルに変更を加えることができるかどうかを示します。 テーブルが更新可能かどうかを簡単に判断するには、 `CDaoTableDef` テーブルのオブジェクトを開き、オブジェクトの [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) メンバー関数を呼び出します。 `CanUpdate` 新しく作成された tabledef オブジェクトに対しては、常に0以外 (TRUE) を返し、アタッチされたテーブルオブジェクトには 0 (FALSE) を返します。 新しい tabledef オブジェクトは、現在のユーザーが書き込み権限を持っているデータベースにのみ追加できます。 テーブルに nonupdatable フィールドのみが含まれている場合、は `CanUpdate` 0 を返します。 1つまたは複数のフィールドが更新可能な場合、は `CanUpdate` 0 以外の値を返します。 編集できるのは、更新可能なフィールドのみです。 詳細については、DAO ヘルプの「更新可能なプロパティ」を参照してください。

*m_lAttributes*<br/>
Tabledef オブジェクトによって表されるテーブルの特性を指定します。 Tabledef の現在の属性を取得するには、その [Getattributes](../../mfc/reference/cdaotabledef-class.md#getattributes) メンバー関数を呼び出します。 返される値は、これらの長い定数の組み合わせにすることができます (ビットごとの or (**&#124;**) 演算子を使用します)。

- `dbAttachExclusive` Microsoft Jet データベースエンジンを使用するデータベースの場合、テーブルは、排他的に使用するために開かれた添付テーブルであることを示します。

- `dbAttachSavePWD` Microsoft Jet データベースエンジンを使用するデータベースの場合、アタッチされたテーブルのユーザー ID とパスワードが接続情報と共に保存されることを示します。

- `dbSystemObject` テーブルが Microsoft Jet データベースエンジンによって提供されるシステムテーブルであることを示します。 システム テーブルは読み取り専用です。

- `dbHiddenObject` テーブルが Microsoft Jet データベースエンジンによって提供される非表示テーブルであることを示します (一時的に使用する場合)。 システム テーブルは読み取り専用です。

- `dbAttachedTable` テーブルが、非 ODBC データベース (Paradox データベースなど) からアタッチされたテーブルであることを示します。

- `dbAttachedODBC` テーブルが、Microsoft SQL Server などの ODBC データベースからアタッチされたテーブルであることを示します。

*m_dateCreated*<br/>
テーブルが作成された日付と時刻。 テーブルが作成された日付を直接取得するに[](../../mfc/reference/cdaotabledef-class.md#getdatecreated)は、 `CDaoTableDef` テーブルに関連付けられているオブジェクトの GetDateCreated メンバー関数を呼び出します。 詳細については、以下のコメントを参照してください。 関連情報については、DAO ヘルプの「DateCreated、LastUpdated Properties」を参照してください。

*m_dateLastUpdated*<br/>
テーブルのデザインに対して行われた最新の変更の日付と時刻。 テーブルが最後に更新された日付を直接取得するには、テーブルに関連付けられているオブジェクトの [Getdatelastupdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) メンバー関数を呼び出し `CDaoTableDef` ます。 詳細については、以下のコメントを参照してください。 関連情報については、DAO ヘルプの「DateCreated、LastUpdated Properties」を参照してください。

*m_strSrcTableName*<br/>
アタッチされたテーブルの名前を指定します (存在する場合)。 ソーステーブル名を直接取得するには、テーブルに関連付けられているオブジェクトの [Getsourcetablename](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) メンバー関数を呼び出し `CDaoTableDef` ます。

*m_strConnect*<br/>
開いているデータベースのソースに関する情報を提供します。 このプロパティを確認するには、オブジェクトの [Getconnect](../../mfc/reference/cdaotabledef-class.md#getconnect) メンバー関数を呼び出し `CDaoTableDef` ます。 接続文字列の詳細については、「」を参照してください `GetConnect` 。

*m_strValidationRule*<br/>
テーブルに変更または追加されたときに、テーブル定義フィールド内のデータを検証する値。 検証は、Microsoft Jet データベースエンジンを使用するデータベースに対してのみサポートされます。 検証規則を直接取得するには、テーブルに関連付けられているオブジェクトの [Getvalidationrule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) メンバー関数を呼び出し `CDaoTableDef` ます。 関連情報については、DAO ヘルプのトピック「ValidationRule プロパティ」を参照してください。

*m_strValidationText*<br/>
ValidationRule プロパティによって指定された検証規則が満たされない場合にアプリケーションで表示する必要があるメッセージのテキストを指定する値。 関連情報については、DAO ヘルプのトピック「ValidationText プロパティ」を参照してください。

*m_lRecordCount*<br/>
Tabledef オブジェクトでアクセスされたレコードの数。 このプロパティ設定は読み取り専用です。 レコード数を直接取得するには、オブジェクトの [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) メンバー関数を呼び出し `CDaoTableDef` ます。 のドキュメントでは、 `GetRecordCount` さらにレコード数について説明しています。 テーブルに多数のレコードが含まれている場合、この数を取得するには時間がかかることに注意してください。

## <a name="remarks"></a>解説

Tabledef は、 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)クラスのオブジェクトです。 上記の Primary、Secondary、および All への参照は、クラスの [Gettableていぎ fo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) メンバー関数によって情報がどのように返されるかを示して `CDaoDatabase` います。

[CDaoDatabase:: Gettableていぎ fo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo)メンバー関数によって取得された情報は、構造体に格納され `CDaoTableDefInfo` ます。 テーブル定義 `GetTableDefInfo` コレクションが格納されている内のオブジェクトのメンバー関数を呼び出し `CDaoDatabase` ます。 `CDaoTableDefInfo` は、 `Dump` デバッグビルドでメンバー関数も定義します。 を使用すると、 `Dump` オブジェクトの内容をダンプでき `CDaoTableDefInfo` ます。

日付と時刻の設定は、ベーステーブルが作成されたコンピューター、または最後に更新されたコンピューターから取得されます。 マルチユーザー環境では、これらの設定をファイルサーバーから直接取得して、DateCreated および LastUpdated プロパティの設定の不一致を回避する必要があります。

## <a name="requirements"></a>要件

**ヘッダー:** afxdao

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック、およびメッセージマップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef クラス](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)
