---
title: ATL HTTP ユーティリティ関数
ms.date: 11/04/2016
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
ms.openlocfilehash: 43813d91daf572ad6094a5a9fe070234e5086593
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481717"
---
# <a name="atl-http-utility-functions"></a>ATL HTTP ユーティリティ関数

これらの関数は、Url の操作をサポートします。

|||
|-|-|
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|安全でない文字とスペースをエスケープ シーケンスに変換を含む URL を正規化します。|
|[AtlCombineUrl](#atlcombineurl)|1 つの正規の URL には、ベース URL と相対 URL を結合します。|
|[AtlEscapeUrl](#atlescapeurl)|すべての安全でない文字をエスケープ シーケンスに変換します。|
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|特定のインターネット プロトコルまたはスキームに関連付けられた既定のポート番号を取得します。|
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|文字を URL で使用しても安全かどうかを判断します。|
|[AtlUnescapeUrl](#atlunescapeurl)|元の値に戻すエスケープ文字を変換します。|
|[RGBToHtml](#rgbtohtml)|変換を[COLORREF](/windows/desktop/gdi/colorref)にその色の値に対応する HTML テキスト値。|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|システム時刻を HTTP ヘッダーで使用できる形式の文字列に変換します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="atlcanonicalizeurl"></a> どうか

URL を標準形式に変換します。安全でない文字や空白をエスケープ シーケンスに変換する処理などが含まれます。

```cpp
inline BOOL AtlCanonicalizeUrl(
   LPCTSTR szUrl,
   LPTSTR szCanonicalized,
   DWORD* pdwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>パラメーター

*szUrl*<br/>
正規化される URL です。

*szCanonicalized*<br/>
正規化された URL を受信する呼び出し元が割り当てたバッファー。

*pdwMaxLength*<br/>
文字の長さを格納する変数へのポインター *szCanonicalized*します。 関数が成功すると、変数は、終端の null 文字を含むバッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、終端の null 文字の空白を含むバッファーのバイトで、必要な長さを受け取ります。

*dwFlags*<br/>
この関数の動作を制御する ATL_URL フラグ。

- 「#」の後に文字をデコードまたはエンコード ATL_URL_BROWSER_MODE しませんまたは"?"と後に後続の空白は削除されません"でしょうか。"。 この値が指定されていない場合は、URL 全体はエンコードされ、後続の空白が削除されます。

- ATL_URL_DECODE では、すべての %XX シーケンスを URL を解析する前に、エスケープ シーケンスを含む文字に変換します。

- パーセント記号をすべて ATL_URL_ENCODE_PERCENT エンコードが発生しました。 既定では、パーセント記号はエンコードされません。

- ATL_URL_ENCODE_SPACES_ONLY エンコード スペースのみです。

- ATL_URL_ESCAPE 変換、対応する文字をすべてのエスケープ シーケンス (%xx を参照)。

- 安全でない文字をエスケープ シーケンスに変換 ATL_URL_NO_ENCODE しません。

- メタ シーケンスは削除 ATL_URL_NO_META されません (など".「と」..")、URL から。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

現在のバージョンのように動作[InternetCanonicalizeUrl](/windows/desktop/api/wininet/nf-wininet-internetcanonicalizeurla) WinInet または Internet Explorer をインストールするのには必要ありません。

### <a name="see-also"></a>関連項目

[InternetCanonicalizeUrl](/windows/desktop/api/wininet/nf-wininet-internetcanonicalizeurla)

## <a name="atlcombineurl"></a> AtlCombineUrl

ベース URL と相対 URL を結合して、1 つの標準形式の URL にします。

```cpp
inline BOOL AtlCombineUrl(
   LPCTSTR szBaseUrl,
   LPCTSTR szRelativeUrl,
   LPTSTR szBuffer,
   DWORD* pdwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>パラメーター

*szBaseUrl*<br/>
ベース URL。

*szRelativeUrl*<br/>
ベース URL の相対 URL です。

*しなかった*<br/>
正規化された URL を受信する呼び出し元が割り当てたバッファー。

*pdwMaxLength*<br/>
文字の長さを格納する変数へのポインター*しなかった*します。 関数が成功すると、変数は、終端の null 文字を含むバッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、終端の null 文字の空白を含むバッファーのバイトで、必要な長さを受け取ります。

*dwFlags*<br/>
この関数の動作を制御するフラグ。 参照してください[どうか](#atlcanonicalizeurl)します。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

現在のバージョンのように動作[InternetCombineUrl](/windows/desktop/api/wininet/nf-wininet-internetcombineurla) WinInet または Internet Explorer をインストールするのには必要ありません。

## <a name="atlescapeurl"></a> AtlEscapeUrl

すべての安全でない文字をエスケープ シーケンスに変換します。

```cpp
inline BOOL AtlEscapeUrl(
   LPCSTR szStringIn,
   LPSTR szStringOut,
   DWORD* pdwStrLen,
   DWORD dwMaxLength,
   DWORD dwFlags = 0) throw();

inline BOOL AtlEscapeUrl(
   LPCWSTR szStringIn,
   LPWSTR szStringOut,
   DWORD* pdwStrLen,
   DWORD dwMaxLength,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>パラメーター

*lpszStringIn*<br/>
変換する URL です。

*lpszStringOut*<br/>
呼び出し元が割り当てたバッファーは変換後の URL が書き込まれます。

*pdwStrLen*<br/>
DWORD 変数へのポインター。 関数が成功すると、 *pdwStrLen*は終端の null 文字を含むバッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、終端の null 文字の空白を含むバッファーのバイトで、必要な長さを受け取ります。 このメソッドは、のワイド文字バージョンを使用して*pdwStrLen*のバイト数ではなくに必要な文字の数を受け取ります。

*dwMaxLength*<br/>
バッファーのサイズ*lpszStringOut*します。

*dwFlags*<br/>
この関数の動作を制御する ATL_URL フラグ。 参照してください[どうか](#atlcanonicalizeurl)使用可能な値。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

## <a name="atlgetdefaulturlport"></a> AtlGetDefaultUrlPort

特定のインターネット プロトコルまたはスキームに関連付けられた、既定のポート番号を取得します。

```
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();
```

### <a name="parameters"></a>パラメーター

*m_nScheme*<br/>
[ATL_URL_SCHEME](atl-url-scheme-enum.md)ポート番号を取得するスキームを示す値。

### <a name="return-value"></a>戻り値

[ATL_URL_PORT](atl-typedefs.md#atl_url_port)スキームが認識されない場合は、指定したスキームまたは ATL_URL_INVALID_PORT_NUMBER に関連付けられています。

## <a name="atlisunsafeurlchar"></a> AtlIsUnsafeUrlChar

URL で使用しても安全な文字かどうかを判断します。

```
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();
```

### <a name="parameters"></a>パラメーター

*chIn*<br/>
安全性をテストする文字。

### <a name="return-value"></a>戻り値

かどうか、入力文字は安全でない、それ以外の場合は TRUE を返します。

### <a name="remarks"></a>Remarks

文字を Url で使用する必要がありますがこの関数を使用してテストすることができを使用して変換[どうか](#atlcanonicalizeurl)します。

## <a name="atlunescapeurl"></a> AtlUnescapeUrl

エスケープされた文字を元の値に変換します。

```cpp
inline BOOL AtlUnescapeUrl(
   LPCSTR szStringIn,
   LPSTR szStringOut,
   LPDWORD pdwStrLen,
   DWORD dwMaxLength) throw();

inline BOOL AtlUnescapeUrl(
   LPCWSTR szStringIn,
   LPWSTR szStringOut,
   LPDWORD pdwStrLen,
   DWORD dwMaxLength) throw();
```

### <a name="parameters"></a>パラメーター

*lpszStringIn*<br/>
変換する URL です。

*lpszStringOut*<br/>
呼び出し元が割り当てたバッファーは変換後の URL が書き込まれます。

*pdwStrLen*<br/>
DWORD 変数へのポインター。 関数が成功すると、変数は、終端の null 文字を含むバッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、終端の null 文字の空白を含むバッファーのバイトで、必要な長さを受け取ります。

*dwMaxLength*<br/>
バッファーのサイズ*lpszStringOut*します。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

によって適用される変換プロセスを反転させます[AtlEscapeUrl](#atlescapeurl)します。

## <a name="rgbtohtml"></a> RGBToHtml

変換を[COLORREF](/windows/desktop/gdi/colorref)にその色の値に対応する HTML テキスト値。

```cpp
bool inline RGBToHtml(
   COLORREF color,
   LPTSTR pbOut,
   long nBuffer);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
RGB 色の値。

*pbOut*<br/>
HTML のカラー値のテキストを受け取る呼び出し元が割り当てたバッファー。 バッファーの領域が必要には少なくとも 8 文字の null 終端文字のスペースを含む)。

*nBuffer*<br/>
(Null 終端文字のスペースを含む) バッファーのバイト サイズ。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

HTML カラー値は、各色の赤、緑、および青のコンポーネントの 2 桁の数字を使用して、6 桁の 16 進値の前にシャープ記号 (例: #FFFFFF は白)。

## <a name="systemtimetohttpdate"></a> SystemTimeToHttpDate

システム時刻を HTTP ヘッダーで使用できる形式の文字列に変換します。

```cpp
inline void SystemTimeToHttpDate(
   const SYSTEMTIME& st,
   CStringA& strTime);
```

### <a name="parameters"></a>パラメーター

*st*<br/>
HTTP の書式指定文字列として取得するシステム時刻。

*strTime*<br/>
RFC 2616 で定義されている HTTP に日付時刻を受け取る文字列変数への参照 ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) および RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt))。

## <a name="see-also"></a>関連項目

[概念](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)
