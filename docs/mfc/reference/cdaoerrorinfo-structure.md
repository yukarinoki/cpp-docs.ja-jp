---
description: '詳細については、次を参照してください: CDaoErrorInfo 構造体'
title: CDaoErrorInfo 構造体
ms.date: 09/17/2019
f1_keywords:
- CDaoErrorInfo
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
ms.openlocfilehash: 3d8ae4bd133c96ef1853c8d087904c7c6eba810d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250960"
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo 構造体

構造体には、 `CDaoErrorInfo` データアクセスオブジェクト (DAO) 用に定義されたエラーオブジェクトに関する情報が含まれています。 DAO 3.6 は最終バージョンであり、互換性のために残されているものと見なされます。

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
数値の DAO エラーコード。 DAO ヘルプの「トラップ可能データアクセスエラー」を参照してください。

*m_strSource*<br/>
最初にエラーを生成したオブジェクトまたはアプリケーションの名前。 Source プロパティは、最初にエラーを生成したオブジェクトを表す文字列式を指定します。式は通常、オブジェクトのクラス名です。 詳細については、DAO ヘルプの「ソースプロパティ」を参照してください。

*m_strDescription*<br/>
エラーに関連付けられている説明文字列。 詳細については、DAO ヘルプの「Description プロパティ」を参照してください。

*m_strHelpFile*<br/>
Microsoft Windows ヘルプファイルへの完全修飾パスです。 詳細については、DAO ヘルプのトピック「HelpContext、HelpFile のプロパティ」を参照してください。

*m_lHelpContext*<br/>
Microsoft Windows ヘルプファイルのトピックのコンテキスト ID。 詳細については、DAO ヘルプのトピック「HelpContext、HelpFile のプロパティ」を参照してください。

## <a name="remarks"></a>解説

MFC では、DAO エラーオブジェクトはクラスにカプセル化されません。 代わりに、 [CDaoException](../../mfc/reference/cdaoexception-class.md) クラスには、DAO オブジェクトに含まれるエラーコレクションにアクセスするためのインターフェイスが用意されてい `DBEngine` ます。このオブジェクトには、すべてのワークスペースも含まれています。 MFC DAO 操作でキャッチされたオブジェクトがスローされると `CDaoException` 、mfc は `CDaoErrorInfo` 構造体にデータを格納し、例外オブジェクトの [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) メンバーに格納します。 (DAO を直接呼び出すことを選択した場合は、例外オブジェクトの [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) メンバー関数を呼び出して入力する必要があり `m_pErrorInfo` ます)。

DAO エラーの処理の詳細については、「 [例外: データベース例外](../../mfc/exceptions-database-exceptions.md)」を参照してください。 関連情報については、DAO ヘルプの「Error オブジェクト」を参照してください。

[CDaoException:: GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo)メンバー関数によって取得された情報は、構造体に格納され `CDaoErrorInfo` ます。 例外ハンドラーでキャッチした`CDaoException`オブジェクトから [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) データメンバーを調べるか、または直接呼び出し中に発生した可能性のあるエラーを確認するために明示的に作成した`CDaoException`オブジェクトから`GetErrorInfo`を呼び出します。を DAO インターフェイスにします。 `CDaoErrorInfo` は、 `Dump` デバッグビルドでメンバー関数も定義します。 を使用すると、 `Dump` オブジェクトの内容をダンプでき `CDaoErrorInfo` ます。

## <a name="requirements"></a>要件

**ヘッダー:** afxdao

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック、およびメッセージマップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoException クラス](../../mfc/reference/cdaoexception-class.md)
