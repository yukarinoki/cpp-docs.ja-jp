---
description: '詳細情報: CGopherLocator クラス'
title: CGopherLocator クラス
ms.date: 11/04/2016
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
ms.openlocfilehash: f615ce6fbda150d923f6664acff207fdebdbba3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184024"
---
# <a name="cgopherlocator-class"></a>CGopherLocator クラス

Gopher "locator" を gopher サーバーから取得し、ロケーターの種類を決定して、ロケーターを [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)で使用できるようにします。

> [!NOTE]
> クラス、 `CGopherConnection` 、 `CGopherFile` `CGopherFileFind` 、 `CGopherLocator` およびそれらのメンバーは、Windows XP プラットフォームでは動作しないため、非推奨とされますが、以前のプラットフォームでも引き続き動作します。

## <a name="syntax"></a>構文

```
class CGopherLocator : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CGopherLocator::CGopherLocator](#cgopherlocator)|`CGopherLocator` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CGopherLocator:: GetLocatorType](#getlocatortype)|Gopher ロケーターを解析し、その属性を決定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CGopherLocator:: operator LPCTSTR](#operator_lpctstr)|`CGopherLocator`C スタイルの文字列としてオブジェクトに格納されている文字に直接アクセスします。|

## <a name="remarks"></a>解説

アプリケーションは、サーバーから情報を取得する前に、gopher サーバーのロケーターを取得する必要があります。 ロケーターがあれば、そのロケーターを不透明なトークンとして扱う必要があります。

各 gopher ロケーターには、検出されたファイルまたはサーバーの種類を決定する属性があります。 Gopher ロケーターの種類の一覧については、「 [Getlocatortype](#getlocatortype) 」を参照してください。

通常、アプリケーションは [CGopherFileFind:: FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) の呼び出しにロケーターを使用して、特定の情報を取得します。

が他の MFC インターネットクラスと連携する方法の詳細については `CGopherLocator` 、「 [WinInet を使用したインターネットプログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>要件

**ヘッダー:** afxinet.h

## <a name="cgopherlocatorcgopherlocator"></a><a name="cgopherlocator"></a> CGopherLocator::CGopherLocator

このメンバー関数は、オブジェクトを作成するために呼び出され `CGopherLocator` ます。

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>パラメーター

*ref*<br/>
定数オブジェクトへの参照 `CGopherLocator` 。

### <a name="remarks"></a>解説

オブジェクトを直接作成することはありません `CGopherLocator` 。 代わりに、 [CGopherConnection:: CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) を呼び出して、オブジェクトへのポインターを作成し、返し `CGopherLocator` ます。

## <a name="cgopherlocatorgetlocatortype"></a><a name="getlocatortype"></a> CGopherLocator:: GetLocatorType

ロケーターの種類を取得するには、このメンバー関数を呼び出します。

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>パラメーター

*dwRef*<br/>
ロケーターの種類を受け取る DWORD への参照。 ロケーターの種類の表については、「 **解説** 」を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数 [GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) を呼び出してエラーの原因を特定することができます。

### <a name="remarks"></a>解説

使用できる型は次のとおりです。

|値|説明|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|ASCII テキストファイル。|
|GOPHER_TYPE_DIRECTORY|追加の Gopher 項目のディレクトリです。|
|GOPHER_TYPE_CSO|CSO 電話帳サーバー。|
|GOPHER_TYPE_ERROR|エラー状態を示します。|
|GOPHER_TYPE_MAC_BINHEX|BINHEX 形式の Macintosh ファイル。|
|GOPHER_TYPE_DOS_ARCHIVE|DOS アーカイブファイル。|
|GOPHER_TYPE_UNIX_UUENCODED|UUENCODE ファイル。|
|GOPHER_TYPE_INDEX_SERVER|インデックスサーバー。|
|GOPHER_TYPE_TELNET|Telnet サーバー。|
|GOPHER_TYPE_BINARY|バイナリファイル。|
|GOPHER_TYPE_REDUNDANT|複製されたサーバー。 に含まれている情報は、プライマリサーバーと重複しています。 プライマリサーバーは、GOPHER_TYPE_REDUNDANT の種類がない最後のディレクトリエントリです。|
|GOPHER_TYPE_TN3270|TN3270 サーバー。|
|GOPHER_TYPE_GIF|GIF グラフィックファイル。|
|GOPHER_TYPE_IMAGE|イメージファイル。|
|GOPHER_TYPE_BITMAP|ビットマップファイル。|
|GOPHER_TYPE_MOVIE|ムービーファイル。|
|GOPHER_TYPE_SOUND|サウンドファイル。|
|GOPHER_TYPE_HTML|HTML ドキュメント。|
|GOPHER_TYPE_PDF|PDF ファイル。|
|GOPHER_TYPE_CALENDAR|カレンダーファイル。|
|GOPHER_TYPE_INLINE|インラインファイル。|
|GOPHER_TYPE_UNKNOWN|項目の種類が不明です。|
|GOPHER_TYPE_ASK|Ask + 項目。|
|GOPHER_TYPE_GOPHER_PLUS|Gopher + 項目。|

## <a name="cgopherlocatoroperator-lpctstr"></a><a name="operator_lpctstr"></a> CGopherLocator:: operator LPCTSTR

この便利なキャスト演算子を使用すると、オブジェクトに格納されている null で終わる C 文字列に効率的にアクセスでき `CGopherLocator` ます。

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>戻り値

文字列のデータへの文字ポインター。

### <a name="remarks"></a>解説

文字はコピーされません。ポインターだけが返されます。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)
