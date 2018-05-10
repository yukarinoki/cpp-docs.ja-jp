---
title: CDaoDatabaseInfo 構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: 7121915671f6e0ab52ae66c53e5ca31fa1faec1c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
 `m_strName`  
 データベース オブジェクトの一意名です。 このプロパティを直接取得するには、する[CDaoDatabase::GetName](../../mfc/reference/cdaodatabase-class.md#getname)です。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 `m_bUpdatable`  
 変更をデータベースにできるかどうかを示します。 このプロパティを直接取得するには、する[CDaoDatabase::CanUpdate](../../mfc/reference/cdaodatabase-class.md#canupdate)です。 詳細については、DAO ヘルプの「更新可能なプロパティ」を参照してください。  
  
 *m_bTransactions*  
 データ ソースがトランザクションをサポートするかどうかを示します: 一連の後でロールバックできる変更の記録 (キャンセル)、またはコミットされた (保存) します。 データベースは、Microsoft Jet データベース エンジンに基づいている場合、トランザクションのプロパティが 0 でないと、トランザクションを使用することができます。 他のデータベース エンジンはトランザクションをサポートしていません。 このプロパティを直接取得するには、する[CDaoDatabase::CanTransact](../../mfc/reference/cdaodatabase-class.md#cantransact)です。 詳細については、DAO ヘルプの「トランザクション プロパティ」を参照してください。  
  
 *m_strVersion*  
 Microsoft Jet データベース エンジンのバージョンを示します。 このプロパティの値を直接取得する呼び出し、データベース オブジェクトの[GetVersion](../../mfc/reference/cdaodatabase-class.md#getversion)メンバー関数。 詳細については、DAO ヘルプの「バージョン プロパティ」を参照してください。  
  
 `m_lCollatingOrder`  
 文字列の比較または並べ替えのためのテキストの並べ替え順序を指定します。 次の値を使用できます。  
  
- **dbSortGeneral** [全般] \(英語、フランス語、ドイツ語、ポルトガル語、イタリア語、および最新のスペイン語) の並べ替え順序を使用します。  
  
- **dbSortArabic**アラビア語の並べ替え順序を使用します。  
  
- **dbSortCyrillic**ロシア語の並べ替え順序を使用します。  
  
- **dbSortCzech**チェコ語の並べ替え順序を使用します。  
  
- **dbSortDutch**オランダ語の並べ替え順序を使用します。  
  
- **dbSortGreek**ギリシャ語の並べ替え順序を使用します。  
  
- **dbSortHebrew**ヘブライ語の並べ替え順序を使用します。  
  
- **dbSortHungarian**ハンガリー語の並べ替え順序を使用します。  
  
- **dbSortIcelandic**アイスランド語の並べ替え順序を使用します。  
  
- **dbSortNorwdan**かノルウェー語、デンマーク語の並べ替え順序を使用します。  
  
- **dbSortPDXIntl** Paradox 国際並べ替え順序を使用します。  
  
- **dbSortPDXNor** Paradox ノルウェー語、デンマーク語の並べ替え順序を使用します。  
  
- **dbSortPDXSwe** Paradox スウェーデン語、フィンランド語の並べ替え順序を使用します。  
  
- **dbSortPolish**ポーランド語の並べ替え順序を使用します。  
  
- **dbSortSpanish**スペイン語の並べ替え順序を使用します。  
  
- **dbSortSwedFin**スウェーデン語/フィンランド語並べ替え順序を使用します。  
  
- **dbSortTurkish**トルコ語の並べ替え順序を使用します。  
  
- **dbSortUndefined**並べ替え順序が未定義であるか、または不明です。  
  
 詳細については、「をカスタマイズする Windows レジストリ設定のデータ アクセス」DAO ヘルプのトピックを参照してください。  
  
 *m_nQueryTimeout*  
 Microsoft Jet データベース エンジンがタイムアウト エラーの前に待機する秒数は、ODBC データベースに、クエリの実行時に発生します。 既定のタイムアウト値は、60 秒です。 QueryTimeout が 0 に設定されている場合は、タイムアウトは行われません。これには、プログラムの応答を停止する可能性があります。 このプロパティの値を直接取得する呼び出し、データベース オブジェクトの[GetQueryTimeout](../../mfc/reference/cdaodatabase-class.md#getquerytimeout)メンバー関数。 詳細については、DAO ヘルプの「QueryTimeout プロパティ」を参照してください。  
  
 `m_strConnect`  
 開いているデータベースのソースに関する情報を提供します。 については、文字列を約接続し、このプロパティの値を直接取得する方法の詳細については、次を参照してください。、 [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect)メンバー関数。 詳細については、"接続 Property"DAO ヘルプのトピックを参照してください。  
  
## <a name="remarks"></a>コメント  
 データベースがクラスの MFC オブジェクトの基になる DAO オブジェクト[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)です。 プライマリ、セカンダリ、および上記のすべての参照は、情報がによって返される方法を示します、 [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo)メンバー関数。  
  
 によって取得される情報、 [CDaoWorkspace::GetDatabaseInfo](../../mfc/reference/cdaoworkspace-class.md#getdatabaseinfo)メンバー関数は、`CDaoDatabaseInfo`構造体。 呼び出す`GetDatabaseInfo`の`CDaoWorkspace`がデータベース コレクション内のデータベース オブジェクトが格納されているオブジェクト。 `CDaoDatabaseInfo` 定義、`Dump`デバッグでメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoDatabaseInfo`オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)
