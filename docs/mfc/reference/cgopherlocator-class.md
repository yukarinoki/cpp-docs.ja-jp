---
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
ms.openlocfilehash: 336997fd4094f4e5e1eb73f467734e40440b63a5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641351"
---
# <a name="cgopherlocator-class"></a>CGopherLocator クラス

Gopher「ロケーター」を gopher サーバーから取得、ロケーターの種類を決定およびロケーターを使用できるように[CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md)します。

> [!NOTE]
>  クラスは、 `CGopherConnection`、 `CGopherFile`、 `CGopherFileFind`、`CGopherLocator`と Windows XP のプラットフォームで機能しませんが、引き続き以前のプラットフォームで動作するため、そのメンバーが使用されなくなりました。

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
|[CGopherLocator::GetLocatorType](#getlocatortype)|Gopher ロケーターを解析し、その属性を決定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CGopherLocator::operator LPCTSTR](#operator_lpctstr)|格納されている文字に直接アクセス、 `CGopherLocator` C スタイル文字列としてオブジェクト。|

## <a name="remarks"></a>Remarks

アプリケーションは、そのサーバーから情報を取得できる前に、gopher サーバーのロケーターを取得する必要があります。 ロケーターは、非透過のトークンとロケーターが処理する必要があります。

各 gopher ロケーターには、ファイルまたはサーバーの種類を決定する属性があります。 参照してください[GetLocatorType](#getlocatortype) gopher ロケーターの種類の一覧についてはします。

アプリケーションへの呼び出しのロケーターを使用する通常[CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile)を特定の情報を取得します。

方法の詳細については、`CGopherLocator`クラスでは、その他の MFC インターネット機能は、記事をご覧ください。[インターネットが WinInet を使用したプログラミング](../../mfc/win32-internet-extensions-wininet.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

##  <a name="cgopherlocator"></a>  CGopherLocator::CGopherLocator

このメンバー関数が作成すると呼ばれる、`CGopherLocator`オブジェクト。

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>パラメーター

*ref*<br/>
定数への参照を`CGopherLocator`オブジェクト。

### <a name="remarks"></a>Remarks

作成することはありません、`CGopherLocator`オブジェクトに直接します。 代わりに、 [CGopherConnection::CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator)を作成してへのポインターを返す、`CGopherLocator`オブジェクト。

##  <a name="getlocatortype"></a>  CGopherLocator::GetLocatorType

ロケーターの種類を取得するには、このメンバー関数を呼び出します。

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>パラメーター

*dwRef*<br/>
ロケーターの種類を受信する DWORD への参照。 参照してください**解説**のロケーターの種類の一覧についてはします。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)エラーの原因を特定するということがあります。

### <a name="remarks"></a>Remarks

使用可能な型は次のとおりです。

|[値]|説明|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|ASCII テキスト ファイル。|
|GOPHER_TYPE_DIRECTORY|Gopher 項目の追加のディレクトリ。|
|GOPHER_TYPE_CSO|CSO 電話帳サーバーです。|
|GOPHER_TYPE_ERROR|エラー状態を示します。|
|GOPHER_TYPE_MAC_BINHEX|BINHEX 形式で Macintosh ファイル。|
|GOPHER_TYPE_DOS_ARCHIVE|DOS のアーカイブ ファイル。|
|GOPHER_TYPE_UNIX_UUENCODED|エンコードされていないファイルです。|
|GOPHER_TYPE_INDEX_SERVER|インデックス サーバー。|
|GOPHER_TYPE_TELNET|Telnet サーバーです。|
|GOPHER_TYPE_BINARY|バイナリ ファイルです。|
|GOPHER_TYPE_REDUNDANT|重複しているサーバー。 含まれる情報は、プライマリ サーバーと重複しています。 プライマリ サーバーは、GOPHER_TYPE_REDUNDANT 型がない最後のディレクトリ エントリです。|
|GOPHER_TYPE_TN3270|TN3270 サーバー。|
|GOPHER_TYPE_GIF|GIF のグラフィック ファイル。|
|GOPHER_TYPE_IMAGE|イメージ ファイル。|
|GOPHER_TYPE_BITMAP|ビットマップ ファイルです。|
|GOPHER_TYPE_MOVIE|ムービー ファイル。|
|GOPHER_TYPE_SOUND|サウンド ファイルです。|
|GOPHER_TYPE_HTML|HTML ドキュメント。|
|GOPHER_TYPE_PDF|PDF ファイルです。|
|GOPHER_TYPE_CALENDAR|予定表ファイルです。|
|GOPHER_TYPE_INLINE|インライン ファイル。|
|GOPHER_TYPE_UNKNOWN|項目の種類が不明です。|
|GOPHER_TYPE_ASK|Ask + 項目。|
|GOPHER_TYPE_GOPHER_PLUS|Gopher + 項目。|

##  <a name="operator_lpctstr"></a>  CGopherLocator::operator LPCTSTR

このキャスト演算子が含まれる null で終わる C 文字列へのアクセスに効率的なメソッドを提供します、`CGopherLocator`オブジェクト。

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>戻り値

文字列のデータを指すポインター。

### <a name="remarks"></a>Remarks

文字はコピーされません。ポインターのみが返されます。

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)
