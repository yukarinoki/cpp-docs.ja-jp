---
title: CDaoErrorInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CDaoErrorInfo
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
ms.openlocfilehash: dd9610fce88c18ac42de81ed712492766ee705de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399851"
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

*m_lErrorCode*<br/>
数値の DAO エラー コードです。 「トラップ可能なデータ アクセス エラー」DAO ヘルプのトピックを参照してください。

*m_strSource*<br/>
オブジェクトまたはアプリケーション エラーの発生源の名前。 ソースのプロパティを最初はエラーを生成したオブジェクトを表す文字列式を指定します式は、通常、オブジェクトのクラス名です。 詳細については、「ソースのプロパティ」DAO ヘルプのトピックを参照してください。

*m_strDescription*<br/>
エラーに関連付けられている説明する文字列。 詳細については、「Description プロパティ」DAO ヘルプのトピックを参照してください。

*m_strHelpFile*<br/>
Microsoft Windows のヘルプ ファイルへの完全修飾パス。 詳細については、DAO のヘルプ トピックの"HelpContext、HelpFile プロパティ"を参照してください。

*m_lHelpContext*<br/>
Microsoft Windows のヘルプ ファイルのトピックのコンテキスト ID。 詳細については、DAO のヘルプ トピックの"HelpContext、HelpFile プロパティ"を参照してください。

## <a name="remarks"></a>Remarks

MFC は、DAO クラスでオブジェクトのエラーをカプセル化しません。 代わりに、 [CDaoException](../../mfc/reference/cdaoexception-class.md)クラスは、DAO に含まれるエラー コレクションにアクセスするためのインターフェイスを提供します。`DBEngine`オブジェクト、すべてのワークスペースが含まれているオブジェクト。 MFC DAO 操作がスローした場合、`CDaoException`をキャッチすることは、MFC は、オブジェクト、`CDaoErrorInfo`構造体であり、例外オブジェクトの格納[m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo)メンバー。 (直接 DAO を呼び出すことを選択する場合は、例外オブジェクトを呼び出す必要があります[GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo)メンバー関数を`m_pErrorInfo`)。

DAO のエラー処理の詳細については、記事を参照してください。[例外。データベース例外](../../mfc/exceptions-database-exceptions.md)します。 関連情報については、「エラー オブジェクト」DAO ヘルプのトピックを参照してください。

によって取得される情報、 [CDaoException::GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo)にメンバー関数が格納されている、`CDaoErrorInfo`構造体。 確認、 [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo)からのデータ メンバーを`CDaoException`、例外ハンドラー、または呼び出しをキャッチするオブジェクト`GetErrorInfo`から、`CDaoException`可能性のあるエラーを確認するために明示的に作成するオブジェクトDAO インターフェイスへの直接の呼び出し中に発生します。 `CDaoErrorInfo` 定義、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoErrorInfo`オブジェクト。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoException クラス](../../mfc/reference/cdaoexception-class.md)
