---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
ms.openlocfilehash: e157a4509fe30b814a1834690a675906ac82afe7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373693"
---
# <a name="cgopherfile-class"></a>クラス

gopher サーバー上のファイルを検索し、読み込む機能が用意されています。

> [!NOTE]
> クラス`CGopherConnection` `CGopherFile`、、`CGopherFileFind``CGopherLocator`およびメンバーは Windows XP プラットフォームでは動作しないため、非推奨になりましたが、以前のプラットフォームでは引き続き動作します。

## <a name="syntax"></a>構文

```
class CGopherFile : public CInternetFile
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[CGopherファイル::CGopherファイル](#cgopherfile)|`CGopherFile` オブジェクトを構築します。|

## <a name="remarks"></a>解説

gopher サービスは、主に情報を検索するためのメニュー駆動型インターフェイスとして機能するため、ユーザーが gopher ファイルにデータを書き込むことを許可しません。 メンバー`CGopherFile`関数`Write`、 `WriteString`、 `Flush` 、 の実装`CGopherFile`は行いません。 オブジェクトに対してこれらの`CGopherFile`関数を呼び出すと[、CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)を返します。

他の MFC`CGopherFile`インターネット クラスとの動作の詳細については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CStdioFile](../../mfc/reference/cstdiofile-class.md)

[CInternetFile](../../mfc/reference/cinternetfile-class.md)

`CGopherFile`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="cgopherfilecgopherfile"></a><a name="cgopherfile"></a>CGopherファイル::CGopherファイル

このメンバー関数は、`CGopherFile`オブジェクトを構築するために呼び出されます。

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

*hファイル*<br/>
HINTERNET ファイルへのハンドル。

*リロケータ*<br/>
[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)オブジェクトへの参照。

*pConnection*<br/>
[オブジェクト](../../mfc/reference/cgopherconnection-class.md)へのポインター。

*hセッション*<br/>
現在のインターネット セッションへのハンドル。

*プストルロケーター*<br/>
gopher サーバーを検索するために使用される文字列へのポインター。 [gopher](cgopherlocator-class.md)ロケーターの詳細については、「Gopher セッション」を参照してください。

*ドロークレン*<br/>
*pstrLocator*のバイト数を含む DWORD。

*dw コンテキスト*<br/>
開かれているファイルのコンテキスト識別子へのポインター。

### <a name="remarks"></a>解説

gopher`CGopherFile`インターネット セッション中にファイルから読み取るオブジェクトが必要です。

オブジェクトを`CGopherFile`直接作成することはありません。 代わりに[、CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile)を呼び出して、gopher サーバー上のファイルを開きます。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cinternetfile-class.md)<br/>
[CGopherLocator クラス](../../mfc/reference/cgopherlocator-class.md)<br/>
[CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)<br/>
[CGopherConnection クラス](../../mfc/reference/cgopherconnection-class.md)
