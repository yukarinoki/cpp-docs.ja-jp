---
title: CDaoDatabaseInfo 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoDatabaseInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoDatabaseInfo structure [MFC]
- DAO (Data Access Objects), Databases collection
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2c70e903e66a34bcb05302ac3732850f9dbb8fa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380790"
---
# <a name="cdaodatabaseinfo-structure"></a>CDaoDatabaseInfo 構造体

`CDaoDatabaseInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているデータベース オブジェクトに関する情報が含まれています。

## <a name="syntax"></a>構文

```
struct CDaoDatabaseInfo
{
    CString m_strName;       // Primary
    BOOL m_bUpdatable;       // Primary
    BOOL m_bTransactions;    // Primary
    CString m_strVersion;    // Secondary
    long m_lCollatingOrder;  // Secondary
    short m_nQueryTimeout;   // Secondary
    CString m_strConnect;    // All
};
```

#### <a name="parameters"></a>パラメーター

*m_strName*<br/>
データベース オブジェクトの一意名します。 このプロパティを直接取得するには、する[CDaoDatabase::GetName](../../mfc/reference/cdaodatabase-class.md#getname)します。 詳細については、「Name プロパティ」DAO ヘルプのトピックを参照してください。

*m_bUpdatable*<br/>
変更をデータベースにできるかどうかを示します。 このプロパティを直接取得するには、する[CDaoDatabase::CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate)します。 詳細については、「DAO ヘルプの「更新可能なプロパティ」」を参照してください。

*m_bTransactions*<br/>
データ ソースがトランザクションをサポートしているかどうかを示します: 一連のロールバックできます。 後で変更の記録 (キャンセル) またはコミット (保存) します。 データベースは、Microsoft Jet データベース エンジンに基づいている場合は、トランザクションのプロパティが 0 以外と、トランザクションを使用することができます。 他のデータベース エンジンはトランザクションをサポートしていません。 このプロパティを直接取得するには、する[CDaoDatabase::CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact)します。 詳細については、「トランザクションのプロパティ」DAO ヘルプのトピックを参照してください。

*m_strVersion*<br/>
Microsoft Jet データベース エンジンのバージョンを示します。 このプロパティの値を直接取得する呼び出し、データベース オブジェクトの[GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion)メンバー関数。 詳細については、「バージョンのプロパティ」DAO ヘルプのトピックを参照してください。

*返さ*<br/>
文字列比較または並べ替え用のテキストの並べ替え順序を指定します。 次の値を使用できます。

- `dbSortGeneral` [全般] (英語、フランス語、ドイツ語、ポルトガル語、イタリア語、および最新のスペイン語) の並べ替え順序を使用します。

- `dbSortArabic` アラビア語の並べ替え順序を使用します。

- `dbSortCyrillic` ロシア語の並べ替え順序を使用します。

- `dbSortCzech` チェコ語の並べ替え順序を使用します。

- `dbSortDutch` オランダ語の並べ替え順序を使用します。

- `dbSortGreek` ギリシャ語の並べ替え順序を使用します。

- `dbSortHebrew` ヘブライ語の並べ替え順序を使用します。

- `dbSortHungarian` ハンガリー語の並べ替え順序を使用します。

- `dbSortIcelandic` アイスランド語の並べ替え順序を使用します。

- `dbSortNorwdan` ノルウェー語、デンマーク語または並べ替え順序を使用します。

- `dbSortPDXIntl` Paradox International の並べ替え順序を使用します。

- `dbSortPDXNor` Paradox ノルウェー語またはデンマーク語の並べ替え順序を使用します。

- `dbSortPDXSwe` Paradox スウェーデンまたはフィンランド語の並べ替え順序を使用します。

- `dbSortPolish` ポーランド語の並べ替え順序を使用します。

- `dbSortSpanish` スペイン語の並べ替え順序を使用します。

- `dbSortSwedFin` スウェーデン語、フィンランド語または並べ替え順序を使用します。

- `dbSortTurkish` トルコ語の並べ替え順序を使用します。

- `dbSortUndefined` 並べ替え順序は、未定義または不明です。

詳細については、"をカスタマイズする Windows レジストリの設定に Data Access"DAO ヘルプのトピックを参照してください。

*m_nQueryTimeout*<br/>
Microsoft Jet データベース エンジンがタイムアウト エラーが発生する前に待機する秒数では、ODBC データベース クエリの実行時に発生します。 既定のタイムアウト値は、60 秒です。 QueryTimeout が 0 に設定されている場合は、タイムアウトは発生しません。これには、プログラムの応答を停止する可能性があります。 このプロパティの値を直接取得する呼び出し、データベース オブジェクトの[GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout)メンバー関数。 詳細については、「QueryTimeout プロパティ」DAO ヘルプのトピックを参照してください。

*m_strConnect*<br/>
開いているデータベースのソースに関する情報を提供します。 については、文字列を約接続し、このプロパティの値を直接取得する方法の詳細については、次を参照してください。、 [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect)メンバー関数。 詳細については、DAO のヘルプ「プロパティの接続」を参照してください。

## <a name="remarks"></a>Remarks

データベースがクラスの MFC オブジェクトを基になる DAO オブジェクト[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)します。 プライマリ、セカンダリ、および上記のすべてへの参照情報がによって返される方法を示すため、 [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo)メンバー関数。

によって取得される情報、 [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo)にメンバー関数が格納されている、`CDaoDatabaseInfo`構造体。 呼び出す`GetDatabaseInfo`の`CDaoWorkspace`がデータベース コレクション内のデータベース オブジェクトが格納されているオブジェクト。 `CDaoDatabaseInfo` 定義、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoDatabaseInfo`オブジェクト。

## <a name="requirements"></a>要件

**ヘッダー:** afxdao.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)
