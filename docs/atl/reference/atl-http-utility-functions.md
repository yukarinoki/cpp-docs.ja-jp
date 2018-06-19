---
title: ATL HTTP ユーティリティ関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 476ca29de5a44e8ebb20d53ec0b88834c7b03eea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363785"
---
# <a name="atl-http-utility-functions"></a>ATL HTTP ユーティリティ関数

これらの関数は、Url の操作をサポートします。

|||  
|-|-|  
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|URL では、安全でない文字や空白をエスケープ シーケンスに変換を正規化します。|  
|[AtlCombineUrl](#atlcombineurl)|1 つの標準形式の URL をベース URL と相対 URL を結合します。|  
|[AtlEscapeUrl](#atlescapeurl)|すべての安全でない文字をエスケープ シーケンスに変換します。|  
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|特定のインターネット プロトコルまたはスキームに関連付けられている既定のポート番号を取得します。|  
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|文字が URL で使用しても安全かどうかを判断します。|  
|[AtlUnescapeUrl](#atlunescapeurl)|変換は、元の値に文字をエスケープします。|  
|[RGBToHtml](#rgbtohtml)|変換、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値をそのカラー値に対応する HTML テキスト。|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|システム時刻を HTTP ヘッダーで使用できる形式の文字列に変換します。|

## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  

## <a name="atlcanonicalizeurl"></a> どうか
URL を標準形式に変換します。安全でない文字や空白をエスケープ シーケンスに変換する処理などが含まれます。  
  
```    
inline BOOL AtlCanonicalizeUrl(  
   LPCTSTR szUrl,  
   LPTSTR szCanonicalized,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `szUrl`  
 正規化される URL です。  
  
 `szCanonicalized`  
 正規化された URL を受信する呼び出し元が割り当てたバッファー。  
  
 `pdwMaxLength`  
 文字の長さを格納する変数へのポインター`szCanonicalized`です。 関数が成功した場合、変数は、終端の null 文字を含むバッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、終端の null 文字用の領域を含むバッファーのバイトで、必要な長さを受け取ります。  
  
 `dwFlags`  
 この関数の動作を制御する ATL_URL フラグ。 

- `ATL_URL_BROWSER_MODE` 「#」の後に文字をデコードまたはエンコードしませんまたは"?"、し、後の末尾の空白文字は削除されません"?"。 この値が指定されていない場合は、URL 全体をエンコードされ、後続の空白が削除されます。
- `ATL_URL_DECODE` 文字、URL が解析される前にエスケープ シーケンスを含むすべての %XX シーケンスに変換します。
- `ATL_URL_ENCODE_PERCENT` 見つかったパーセント記号を任意にエンコードします。 既定では、パーセント記号はエンコードされていません。
- `ATL_URL_ENCODE_SPACES_ONLY` 空白文字のみをエンコードします。
- `ATL_URL_ESCAPE` すべてのエスケープ シーケンス (%xx) を対応する文字に変換します。
- `ATL_URL_NO_ENCODE` 安全でない文字をエスケープ シーケンスは変換されません。
- `ATL_URL_NO_META` メタ シーケンスは削除されません (など"です。"と"..")、URL からです。 
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 現在のバージョンのように動作[InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342) WinInet または Internet Explorer をインストールする必要はありません。  
  
### <a name="see-also"></a>関連項目  
 [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342)

 ## <a name="atlcombineurl"></a> AtlCombineUrl
 ベース URL と相対 URL を結合して、1 つの標準形式の URL にします。  
  
```    
inline BOOL AtlCombineUrl(  
   LPCTSTR szBaseUrl,  
   LPCTSTR szRelativeUrl,  
   LPTSTR szBuffer,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *szBaseUrl*  
 ベース URL。  
  
 *szRelativeUrl*  
 ベース URL に対する相対 URL です。  
  
 `szBuffer`  
 正規化された URL を受信する呼び出し元が割り当てたバッファー。  
  
 `pdwMaxLength`  
 文字の長さを格納する変数へのポインター`szBuffer`です。 関数が成功した場合、変数は、終端の null 文字を含むバッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、終端の null 文字用の領域を含むバッファーのバイトで、必要な長さを受け取ります。  
  
 `dwFlags`  
 この関数の動作を制御するフラグ。 参照してください[どうか](#atlcanonicalizeurl)です。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 現在のバージョンのように動作[InternetCombineUrl](http://msdn.microsoft.com/library/windows/desktop/aa384355) WinInet または Internet Explorer をインストールする必要はありません。  
  
## <a name="atlescapeurl"></a> AtlEscapeUrl
 すべての安全でない文字をエスケープ シーケンスに変換します。  
  
```    
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
 `lpszStringIn`  
 変換する URL です。  
  
 `lpszStringOut`  
 変換された URL の書き込み先となる、呼び出し元が割り当てたバッファー。  
  
 `pdwStrLen`  
 DWORD 変数へのポインター。 関数が成功すると、`pdwStrLen`終端の null 文字を含むバッファーに書き込まれた文字数を受け取る。 関数が失敗した場合、変数は、終端の null 文字用の領域を含むバッファーのバイトで、必要な長さを受け取ります。 このメソッドのワイド文字バージョンを使用して`pdwStrLen`受信、必要な文字数、バイト数ではありません。  
  
 `dwMaxLength`  
 バッファーのサイズ`lpszStringOut`です。  
  
 `dwFlags`  
 この関数の動作を制御する ATL_URL フラグ。 参照してください[どうか](#atlcanonicalizeurl)使用可能な値です。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
## <a name="atlgetdefaulturlport"></a> 
 特定のインターネット プロトコルまたはスキームに関連付けられた、既定のポート番号を取得します。  
  
```  
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *m_nScheme*  
 [ATL_URL_SCHEME](atl-url-scheme-enum.md)ポート番号を取得するパターンを識別する値。  
  
### <a name="return-value"></a>戻り値  
 [ATL_URL_PORT](atl-typedefs.md#atl_url_port)スキームが認識されない場合は、指定されたスキームまたは ATL_URL_INVALID_PORT_NUMBER に関連付けられています。  

## <a name="atlisunsafeurlchar"></a> AtlIsUnsafeUrlChar
 URL で使用しても安全な文字かどうかを判断します。  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `chIn`  
 安全性をテストする文字。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**入力文字が安全でない場合**FALSE**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 Url で使用する必要があります文字は、この関数を使用してテストしてを使用して変換[どうか](#atlcanonicalizeurl)です。  
  
## <a name="atlunescapeurl"></a> AtlUnescapeUrl
 エスケープされた文字を元の値に変換します。  
  
```    
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
 `lpszStringIn`  
 変換する URL です。  
  
 `lpszStringOut`  
 変換された URL の書き込み先となる、呼び出し元が割り当てたバッファー。  
  
 `pdwStrLen`  
 DWORD 変数へのポインター。 関数が成功した場合、変数は、終端の null 文字を含むバッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、終端の null 文字用の領域を含むバッファーのバイトで、必要な長さを受け取ります。  
  
 `dwMaxLength`  
 バッファーのサイズ`lpszStringOut`です。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 によって適用される変換プロセスを反転させます[AtlEscapeUrl](#atlescapeurl)です。  
  
## <a name="rgbtohtml"></a> RGBToHtml
変換、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値をそのカラー値に対応する HTML テキスト。  
  
```  
bool inline RGBToHtml(  
   COLORREF color,  
   LPTSTR pbOut,  
   long nBuffer);  
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 色の RGB 値。  
  
 `pbOut`  
 HTML のカラー値のテキストを受信する呼び出し元が割り当てたバッファー。 バッファーの領域が必要には、少なくとも 8 文字の null 終端文字のスペースを含む)。  
  
 *nBuffer*  
 (Null 終端文字のスペースを含む) バッファーのバイト サイズ。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 HTML 色の値は、各色の赤、緑、および青のコンポーネントの 2 桁の数字を使用して、6 桁の 16 進値の前にシャープ記号 (例: #FFFFFF の色は白)。  
  
## <a name="systemtimetohttpdate"></a> SystemTimeToHttpDate
システム時刻を HTTP ヘッダーで使用できる形式の文字列に変換します。  
  
```  
inline void SystemTimeToHttpDate( 
   const SYSTEMTIME& st,  
   CStringA& strTime);  
```  
  
### <a name="parameters"></a>パラメーター  
 `st`  
 HTTP 書式指定文字列として取得するためのシステム時刻。  
  
 *strTime*  
 RFC 2616 で定義された、HTTP 日付時刻を受け取る文字列変数への参照を ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) および RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt))。  
  
## <a name="see-also"></a>関連項目  
 [概念](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)   

