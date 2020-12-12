---
description: '詳細情報: CGopherFile クラス'
title: CGopherFile クラス
ms.date: 11/04/2016
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
ms.openlocfilehash: 8f511bdaf3ae6417972ea19465c0392832a2b408
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184076"
---
# <a name="cgopherfile-class"></a>CGopherFile クラス

gopher サーバー上のファイルを検索し、読み込む機能が用意されています。

> [!NOTE]
> クラス、 `CGopherConnection` 、 `CGopherFile` `CGopherFileFind` 、 `CGopherLocator` およびそれらのメンバーは、Windows XP プラットフォームでは動作しないため、非推奨とされますが、以前のプラットフォームでも引き続き動作します。

## <a name="syntax"></a>構文

```
class CGopherFile : public CInternetFile
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CGopherFile:: CGopherFile](#cgopherfile)|`CGopherFile` オブジェクトを構築します。|

## <a name="remarks"></a>解説

このサービスは主に情報を検索するためのメニュー主導のインターフェイスとして機能するため、gopher サービスでは、ユーザーが gopher ファイルにデータを書き込むことを許可していません。 `CGopherFile`メンバー関数、 `Write` `WriteString` 、およびは、に対して実装されて `Flush` いません `CGopherFile` 。 オブジェクトに対してこれらの関数を呼び出すと `CGopherFile` 、 [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)が返されます。

が他の MFC インターネットクラスと連携する方法の詳細については `CGopherFile` 、「 [WinInet を使用したインターネットプログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CGopherFile`

## <a name="requirements"></a>要件

**ヘッダー:** afxinet.h

## <a name="cgopherfilecgopherfile"></a><a name="cgopherfile"></a> CGopherFile:: CGopherFile

このメンバー関数は、オブジェクトを構築するために呼び出され `CGopherFile` ます。

```
CGopherFile(
    HINTERNET hFile,
    CGopherLocator& refLocator,
    CGopherConnection* pConnection);

CGopherFile(
    HINTERNET hFile,
    HINTERNET hSession,
    LPCTSTR pstrLocator,
    DWORD dwLocLen,
    DWORD_PTR dwContext);
```

### <a name="parameters"></a>パラメーター

*hFile*<br/>
HINTERNET ファイルへのハンドル。

*refLocator*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)オブジェクトへの参照。

*pConnection*<br/>
[CGopherConnection](../../mfc/reference/cgopherconnection-class.md)オブジェクトへのポインター。

*hSession*<br/>
現在のインターネットセッションを対象としたハンドル。

*pstrLocator*<br/>
Gopher サーバーを検索するために使用する文字列へのポインター。 Gopher ロケーターの詳細については、「 [Gopher セッション](cgopherlocator-class.md) 」を参照してください。

*dwLocLen*<br/>
*PstrLocator* のバイト数を格納している DWORD。

*dwContext*<br/>
開かれているファイルのコンテキスト識別子へのポインター。

### <a name="remarks"></a>解説

`CGopherFile`Gopher インターネットセッション中にファイルから読み取るオブジェクトが必要です。

オブジェクトを直接作成することはありません `CGopherFile` 。 代わりに、 [CGopherConnection:: OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) を呼び出して、gopher サーバー上のファイルを開きます。

## <a name="see-also"></a>関連項目

[CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CInternetFile クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherLocator クラス](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CGopherConnection クラス](../../mfc/reference/cgopherconnection-class.md)
