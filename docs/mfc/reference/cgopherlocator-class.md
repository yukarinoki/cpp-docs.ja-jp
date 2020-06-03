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
ms.openlocfilehash: d23ef3dad68c62e74ec64454953ca372b8c31114
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373675"
---
# <a name="cgopherlocator-class"></a>CGopherLocator クラス

gopher サーバーから gopher "ロケーター" を取得し、ロケーターのタイプを決定し、ロケーターを[CGopherFileFind で](../../mfc/reference/cgopherfilefind-class.md)使用できるようにします。

> [!NOTE]
> クラス`CGopherConnection` `CGopherFile`、、`CGopherFileFind``CGopherLocator`およびメンバーは Windows XP プラットフォームでは動作しないため、非推奨になりましたが、以前のプラットフォームでは引き続き動作します。

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
|[CGopherLocator::ゲットロケータータイプ](#getlocatortype)|gopher ロケーターを解析し、その属性を決定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[コファーロケーター::オペレーター LPCTSTR](#operator_lpctstr)|オブジェクトに格納されている文字に`CGopherLocator`C スタイルの文字列として直接アクセスします。|

## <a name="remarks"></a>解説

アプリケーションは、そのサーバーから情報を取得する前に、gopher サーバーのロケーターを取得する必要があります。 ロケーターを取得したら、そのロケーターを不透明なトークンとして扱う必要があります。

各 gopher ロケーターには、検出されたファイルまたはサーバーのタイプを決定する属性があります。 ゴファー ロケーターの種類の一覧については[、「GetLocatorType」](#getlocatortype)を参照してください。

アプリケーションは通常[、CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile)への呼び出しにロケーターを使用して、特定の情報を取得します。

他の MFC`CGopherLocator`インターネット クラスとの動作の詳細については[、「WinInet を使用したインターネット プログラミング](../../mfc/win32-internet-extensions-wininet.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CGopherLocator`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxinet.h

## <a name="cgopherlocatorcgopherlocator"></a><a name="cgopherlocator"></a>CGopherLocator::CGopherLocator

このメンバー関数は、`CGopherLocator`オブジェクトを作成するために呼び出されます。

```
CGopherLocator(const CGopherLocator& ref);
```

### <a name="parameters"></a>パラメーター

*ref*<br/>
定数`CGopherLocator`オブジェクトへの参照。

### <a name="remarks"></a>解説

オブジェクトを`CGopherLocator`直接作成することはありません。 代わりに[、CGopherConnection::CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator)を呼び出して`CGopherLocator`オブジェクトへのポインターを作成して返します。

## <a name="cgopherlocatorgetlocatortype"></a><a name="getlocatortype"></a>CGopherLocator::ゲットロケータータイプ

ロケーターの種類を取得します。

```
BOOL GetLocatorType(DWORD& dwRef) const;
```

### <a name="parameters"></a>パラメーター

*ドフレファ*<br/>
ロケーターの種類を受け取る DWORD への参照。 ロケーター タイプのテーブルについては **、「解説」** を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。 呼び出しが失敗した場合は、Win32 関数[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)が呼び出され、エラーの原因を特定できます。

### <a name="remarks"></a>解説

可能な型は次のとおりです。

|[値]|意味|
|-----------|-------------|
|GOPHER_TYPE_TEXT_FILE|ASCII テキスト ファイル。|
|GOPHER_TYPE_DIRECTORY|追加の Gopher 項目のディレクトリ。|
|GOPHER_TYPE_CSO|CSO 電話帳サーバー。|
|GOPHER_TYPE_ERROR|エラー状態を示します。|
|GOPHER_TYPE_MAC_BINHEX|BINHEX 形式のマッキントッシュ ファイル。|
|GOPHER_TYPE_DOS_ARCHIVE|DOS アーカイブ ファイル。|
|GOPHER_TYPE_UNIX_UUENCODED|UUENCODE ファイル。|
|GOPHER_TYPE_INDEX_SERVER|インデックス サーバー。|
|GOPHER_TYPE_TELNET|Telnet サーバー。|
|GOPHER_TYPE_BINARY|バイナリ ファイル。|
|GOPHER_TYPE_REDUNDANT|複製されたサーバー。 に含まれる情報は、プライマリ サーバーの複製です。 プライマリ サーバーは、GOPHER_TYPE_REDUNDANTタイプを持たない最後のディレクトリ エントリです。|
|GOPHER_TYPE_TN3270|TN3270 サーバー。|
|GOPHER_TYPE_GIF|GIF グラフィック ファイル。|
|GOPHER_TYPE_IMAGE|イメージ ファイル。|
|GOPHER_TYPE_BITMAP|ビットマップ ファイル。|
|GOPHER_TYPE_MOVIE|ムービー ファイル。|
|GOPHER_TYPE_SOUND|サウンド ファイル。|
|GOPHER_TYPE_HTML|HTML ドキュメント。|
|GOPHER_TYPE_PDF|PDF ファイル。|
|GOPHER_TYPE_CALENDAR|カレンダー ファイル。|
|GOPHER_TYPE_INLINE|インライン ファイル。|
|GOPHER_TYPE_UNKNOWN|項目の種類が不明です。|
|GOPHER_TYPE_ASK|Ask+ アイテム。|
|GOPHER_TYPE_GOPHER_PLUS|ゴファー+アイテム。|

## <a name="cgopherlocatoroperator-lpctstr"></a><a name="operator_lpctstr"></a>コファーロケーター::オペレーター LPCTSTR

この便利なキャスト演算子は、オブジェクトに含まれる null で終わる C`CGopherLocator`文字列にアクセスするための効率的な方法を提供します。

```
operator LPCTSTR () const;
```

### <a name="return-value"></a>戻り値

文字列のデータへの文字ポインター。

### <a name="remarks"></a>解説

文字はコピーされません。ポインターのみが返されます。

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CGopherFileFind クラス](../../mfc/reference/cgopherfilefind-class.md)
