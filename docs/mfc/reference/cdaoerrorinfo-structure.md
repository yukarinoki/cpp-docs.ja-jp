---
title: CDaoErrorInfo 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 787e9d5ac860e283d6eacc0f22b790a6196485f4
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335569"
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo 構造体
`CDaoErrorInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているエラー オブジェクトに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoErrorInfo  
{  
    long m_lErrorCode;  
    CString m_strSource;  
    CString m_strDescription;  
    CString m_strHelpFile;  
    long m_lHelpContext;  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 *m_lErrorCode*  
 数値の DAO エラー コードです。 「トラップ可能なデータ アクセス エラー」DAO ヘルプのトピックを参照してください。  
  
 *m_strSource*  
 オブジェクトまたはアプリケーション エラーの発生源の名前。 ソースのプロパティを最初はエラーを生成したオブジェクトを表す文字列式を指定します式は、通常、オブジェクトのクラス名です。 詳細については、「ソースのプロパティ」DAO ヘルプのトピックを参照してください。  
  
 *m_strDescription*  
 エラーに関連付けられている説明する文字列。 詳細については、「Description プロパティ」DAO ヘルプのトピックを参照してください。  
  
 *m_strHelpFile*  
 Microsoft Windows のヘルプ ファイルへの完全修飾パス。 詳細については、DAO のヘルプ トピックの"HelpContext、HelpFile プロパティ"を参照してください。  
  
 *m_lHelpContext*  
 Microsoft Windows のヘルプ ファイルのトピックのコンテキスト ID。 詳細については、DAO のヘルプ トピックの"HelpContext、HelpFile プロパティ"を参照してください。  
  
## <a name="remarks"></a>Remarks  
 MFC は、DAO クラスでオブジェクトのエラーをカプセル化しません。 代わりに、 [CDaoException](../../mfc/reference/cdaoexception-class.md)クラスは、DAO に含まれるエラー コレクションにアクセスするためのインターフェイスを提供します。`DBEngine`オブジェクト、すべてのワークスペースが含まれているオブジェクト。 MFC DAO 操作がスローした場合、`CDaoException`をキャッチすることは、MFC は、オブジェクト、`CDaoErrorInfo`構造体であり、例外オブジェクトの格納[m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo)メンバー。 (直接 DAO を呼び出すことを選択する場合は、例外オブジェクトを呼び出す必要があります[GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo)メンバー関数を`m_pErrorInfo`)。  
  
 DAO のエラー処理の詳細については、記事を参照してください。[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)します。 関連情報については、「エラー オブジェクト」DAO ヘルプのトピックを参照してください。  
  
 によって取得される情報、 [CDaoException::GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo)にメンバー関数が格納されている、`CDaoErrorInfo`構造体。 確認、 [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo)からのデータ メンバーを`CDaoException`、例外ハンドラー、または呼び出しをキャッチするオブジェクト`GetErrorInfo`から、`CDaoException`可能性のあるエラーを確認するために明示的に作成するオブジェクトDAO インターフェイスへの直接の呼び出し中に発生します。 `CDaoErrorInfo` 定義、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoErrorInfo`オブジェクト。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)
