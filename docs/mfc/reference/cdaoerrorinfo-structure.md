---
title: CDaoErrorInfo 構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: 4c11ebaa7d315d09cea40b4ddc94d5afff498bf7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
 数値の DAO エラー コードです。 「トラップできるデータ アクセス エラー」DAO ヘルプのトピックを参照してください。  
  
 *m_strSource*  
 最初に発生したエラーをオブジェクトまたはアプリケーションの名前。 基になるプロパティです。 エラーの発生源オブジェクトを表す文字列式を指定します。式は、通常、オブジェクトのクラス名です。 詳細については、DAO ヘルプの「ソース プロパティ」を参照してください。  
  
 *m_strDescription*  
 エラーに関連付けられているわかりやすい文字列。 詳細については、DAO ヘルプの「説明プロパティ」を参照してください。  
  
 *m_strHelpFile*  
 Microsoft Windows のヘルプ ファイルへの完全修飾パス。 詳細については、DAO のヘルプ トピック「HelpContext、HelpFile プロパティ」を参照してください。  
  
 *m_lHelpContext*  
 Microsoft Windows のヘルプ ファイルのトピックのコンテキスト ID です。 詳細については、DAO のヘルプ トピック「HelpContext、HelpFile プロパティ」を参照してください。  
  
## <a name="remarks"></a>コメント  
 MFC は、DAO クラスでオブジェクトのエラーをカプセル化しません。 代わりに、 [CDaoException](../../mfc/reference/cdaoexception-class.md)クラスは、DAO に含まれるエラー コレクションにアクセスするためのインターフェイスを提供します。 **DBEngine**オブジェクト、すべてのワークスペースが含まれているオブジェクト。 MFC DAO 操作がスローした場合、`CDaoException`オブジェクトをキャッチすることは、MFC は、`CDaoErrorInfo`構造体し、例外オブジェクトの格納[m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo)メンバー。 (DAO を直接呼び出す場合は、呼び出す必要がありますは例外オブジェクトの[GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo)メンバー関数は、入力を自分で`m_pErrorInfo`)。  
  
 DAO のエラー処理の詳細については、記事を参照してください。[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)です。 関連情報については、DAO ヘルプの「エラー オブジェクト」を参照してください。  
  
 によって取得される情報、 [CDaoException::GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo)メンバー関数は、`CDaoErrorInfo`構造体。 確認、 [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo)からそのデータ メンバー、`CDaoException`例外ハンドラー、または呼び出しでキャッチするオブジェクト`GetErrorInfo`から、`CDaoException`可能性のあるエラーを確認するために明示的に作成したオブジェクトDAO インターフェイスへの直接の呼び出し中に発生します。 `CDaoErrorInfo` 定義、`Dump`デバッグでメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoErrorInfo`オブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)
