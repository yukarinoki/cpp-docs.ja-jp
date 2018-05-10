---
title: ATL テキストエンコーディング関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlGetHexValue
- atlbase/ATL::AtlGetVersion
- atlenc/ATL::AtlHexDecode
- atlenc/ATL::AtlHexDecodeGetRequiredLength
- atlenc/ATL::AtlHexEncode
- atlenc/ATL::AtlHexEncodeGetRequiredLength
- atlenc/ATL::AtlHexValue
- atlenc/ATL::BEncode
- atlenc/ATL::BEncodeGetRequiredLength
- atlenc/ATL::EscapeXML
- atlenc/ATL::GetExtendedChars
- atlenc/ATL::IsExtendedChar
- atlenc/ATL::QEncode
- atlenc/ATL::QEncodeGetRequiredLength
- atlenc/ATL::QPDecode
- atlenc/ATL::QPDecodeGetRequiredLength
- atlenc/ATL::QPEncode
- atlenc/ATL::QPEncodeGetRequiredLength
- atlenc/ATL::UUDecode
- atlenc/ATL::UUDecodeGetRequiredLength
- atlenc/ATL::UUEncode
- atlenc/ATL::UUEncodeGetRequiredLength
ms.assetid: 2ae1648b-2b87-4112-92aa-0069fcfd23da
ms.openlocfilehash: 26eb0709c4009070e6255c6ee178f19d13d8a9c3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="atl-text-encoding-functions"></a>ATL テキストエンコーディング関数
これらの関数は、テキスト エンコードとデコードをサポートします。

|||  
|-|-|  
|[AtlGetHexValue](#atlgethexvalue)|16 進数の数値を取得します。|   
|[AtlGetVersion](#atlgetversion)|使用している ATL ライブラリのバージョンを取得するには、この関数を呼び出します。  |  
|[AtlHexDecode](#atlhexdecode)|前の呼び出しによって 16 進テキストとしてエンコードされているデータの文字列をデコード[AtlHexEncode](#atlhexencode)です。|
|[AtlHexDecodeGetRequiredLength](#atlhexdecodegetrequiredlength)|指定した長さの 16 進エンコードされた文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|
|[AtlHexEncode](#atlhexencode)|一部のデータを 16 進テキストの文字列としてエンコードします。|
|[AtlHexEncodeGetRequiredLength](#atlhexencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[AtlHexValue](#atlhexvalue)|16 進数の数値を取得します。 |
|[AtlUnicodeToUTF8](#atlunicodetoutf8)|Unicode 文字列を UTF-8 に変換します。 |
|[BEncode](#bencode)|"B" エンコーディングを使用して一部のデータを変換します。|
|[BEncodeGetRequiredLength](#bencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[EscapeXML](#escapexml)|XML での使用には安全でない文字を安全な文字に変換します。|
|[GetExtendedChars](#getextendedchars)|文字列に含まれる拡張文字の数を取得します。|
|[IsExtendedChar](#isextendedchar)|指定された文字が拡張文字 (文字コードが 31 以下または 127 以上で、タブ、ラインフィード、キャリッジ リターン以外の文字) かどうかを判断します。|
|[QEncode](#qencode)|"Q" エンコーディングを使用して一部のデータを変換します。  |
|[QEncodeGetRequiredLength](#qencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[QPDecode](#qpdecode)|前の呼び出しによってなど quoted-printable 形式にエンコードされたデータの文字列をデコード[QPEncode](#qpencode)です。|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|quoted-printable にエンコードされた指定長の文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|
|[QPEncode](#qpencode)|一部のデータを quoted-printable 形式にエンコードします。|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[UUDecode](#uudecode)|など、以前の呼び出しによって uuencode されているデータの文字列をデコード[UUEncode](#uuencode)です。|
|[UUDecodeGetRequiredLength](#uudecodegetrequiredlength)|指定した長さの uuencode された文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|
|[UUEncode](#uuencode)|データを uuencode します。 |
|[UUEncodeGetRequiredLength](#uuencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|

## <a name="requirements"></a>要件  
 **ヘッダー:** atlenc.h  
 
## <a name="atlgethexvalue"></a> AtlGetHexValue
16 進数の数値を取得します。  
  
```    
inline char AtlGetHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `chIn`  
 16 進数の文字 '0' ~ '9'、'A'-'F' または 'a'-'f' です。  
  
### <a name="return-value"></a>戻り値  
 入力文字の数値の値は、16 進数として解釈されます。 たとえば、'0' の入力が 0 の値を返し、'A' の入力が 10 の値を返します。 入力文字が 16 進数でない場合は、この関数は-1 を返します。  
  
## <a name="atlgetversion"></a> AtlGetVersion
使用している ATL ライブラリのバージョンを取得するには、この関数を呼び出します。  
  
```  
ATLAPI_(DWORD) AtlGetVersion(void* pReserved);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pReserved`  
 予約済みのポインター。  
  
### <a name="return-value"></a>戻り値  
 返します、`DWORD`コンパイルまたは実行されている、ATL ライブラリのバージョンの整数値。  
  
## <a name="example"></a>例  
 関数は、次のように呼び出す必要があります。  
  
 [!code-cpp[NVC_ATL_Utilities#95](../../atl/codesnippet/cpp/atl-text-encoding-functions_1.cpp)]  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  

## <a name="atlhexdecode"></a> AtlHexDecode
前の呼び出しによって 16 進テキストとしてエンコードされているデータの文字列をデコード[AtlHexEncode](#atlhexencode)です。  
  
```    
inline BOOL AtlHexDecode(  
   LPCSTR pSrcData,  
   int nSrcLen,  
   LPBYTE pbDest,  
   int* pnDestLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pSrcData`  
 デコードするデータを含む文字列。  
  
 `nSrcLen`  
 文字の長さ`pSrcData`です。  
  
 `pbDest`  
 デコードされたデータを受信する呼び出し元が割り当てたバッファー。  
  
 `pnDestLen`  
 長さのバイト数を格納する変数へのポインター`pbDest`です。 関数が成功した場合、変数は、バッファーに書き込まれたバイト数を受け取ります。 関数が失敗した場合、変数は、バッファーのバイトで、必要な長さを受け取ります。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
## <a name="atlhexdecodegetrequiredlength"></a> AtlHexDecodeGetRequiredLength
指定した長さの 16 進エンコードされた文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。  
  
```  
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードされた文字列の文字の数。  
  
### <a name="return-value"></a>戻り値  
 デコードされた文字列を格納するバッファーの必要なバイト数`nSrcLen`文字です。  
  
## <a name="atlhexencode"></a> AtlHexEncode
一部のデータを 16 進テキストの文字列としてエンコードします。  
  
```  
inline BOOL AtlHexEncode(  
   const BYTE * pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
int * pnDestLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pbSrcData`  
 エンコードするデータを保持するバッファー。  
  
 `nSrcLen`  
 エンコードするデータの長さをバイト単位で。  
  
 `szDest`  
 エンコードされたデータを受信する呼び出し元が割り当てたバッファー。  
  
 `pnDestLen`  
 文字の長さを格納する変数へのポインター`szDest`です。 関数が成功した場合、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 ソース データの各バイトは、2 つの 16 進文字としてエンコードされます。  
  
## <a name="atlhexencodegetrequiredlength"></a> AtlHexEncodeGetRequiredLength
指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。  
  
```  
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードするデータのバイト数。  
  
### <a name="return-value"></a>戻り値  
 文字のエンコードされたデータを格納するバッファーのために必要な数`nSrcLen`バイトです。  
  
## <a name="atlhexvalue"></a> AtlHexValue
16 進数の数値を取得します。  
  
```  
inline short AtlHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `chIn`  
 16 進数の文字 '0' ~ '9'、'A'-'F' または 'a'-'f' です。  
  
### <a name="return-value"></a>戻り値  
 入力文字の数値の値は、16 進数として解釈されます。 たとえば、'0' の入力が 0 の値を返し、'A' の入力が 10 の値を返します。 入力文字が 16 進数でない場合は、この関数は-1 を返します。  
  
## <a name="atlunicodetoutf8"></a> AtlUnicodeToUTF8
Unicode 文字列を UTF-8 に変換します。  
  
```  
ATL_NOINLINE inline int AtlUnicodeToUTF8(  
   LPCWSTR wszSrc,  
   int nSrc,  
   LPSTR szDest,  
   int nDest) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *wszSrc*  
 変換する Unicode 文字列  
  
 `nSrc`  
 Unicode 文字列の文字の長さ。  
  
 `szDest`  
 変換後の文字列を受信する呼び出し元が割り当てたバッファー。  
  
 `nDest`  
 バッファーの長さをバイト単位です。  
  
### <a name="return-value"></a>戻り値  
 変換後の文字列の文字の数を返します。  
  
### <a name="remarks"></a>コメント  
 変換後の文字列に必要なバッファーのサイズを調べるには、この関数 0 を渡す`szDest`と`nDest`です。  
  
## <a name="bencode"></a> BEncode  
"B" エンコーディングを使用して一部のデータを変換します。  
  
```  
inline BOOL BEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCSTR pszCharSet) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pbSrcData`  
 エンコードするデータを保持するバッファー。  
  
 `nSrcLen`  
 エンコードするデータの長さをバイト単位で。  
  
 `szDest`  
 エンコードされたデータを受信する呼び出し元が割り当てたバッファー。  
  
 `pnDestLen`  
 文字の長さを格納する変数へのポインター`szDest`です。 関数が成功した場合、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。  
  
 `pszCharSet`  
 文字変換を使用するセットします。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 "B"エンコーディング方式については、「RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt))。  
  
## <a name="bencodegetrequiredlength"></a> BEncodeGetRequiredLength 
指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。  
  
```  
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードするデータのバイト数。  
  
 `nCharsetLen`  
 変換を使用する文字セットの文字の長さ。  
  
### <a name="return-value"></a>戻り値  
 文字のエンコードされたデータを格納するバッファーのために必要な数`nSrcLen`バイトです。  
  
### <a name="remarks"></a>コメント  
 "B"エンコーディング方式については、「RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt))。  
  
## <a name="escapexml"></a> EscapeXML
XML での使用には安全でない文字を安全な文字に変換します。  
  
```  
inline int EscapeXML(  
   const wchar_t * szIn,  
   int nSrcLen,  
   wchar_t * szEsc,  
   int nDestLen,  
   DWORD dwFlags = ATL_ESC_FLAG_NONE) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `szIn`  
 変換対象の文字列。  
  
 *nSrclen*  
 変換対象の文字列の文字の長さ。  
  
 *szEsc*  
 変換後の文字列を受信する呼び出し元が割り当てたバッファー。  
  
 *nDestLen*  
 呼び出し元が割り当てたバッファーの文字の長さ。  
  
 `dwFlags`  
 変換の実行方法を記述する ATL_ESC フラグ。 

- `ATL_ESC_FLAG_NONE` 既定の動作です。 引用符記号とアポストロフィは変換されません。
- `ATL_ESC_FLAG_ATTR` 記号とアポストロフィに変換されます見積もり`&quot;`と`&apos;`それぞれします。


  
### <a name="return-value"></a>戻り値  
 変換後の文字列の文字の長さ。  
  
### <a name="remarks"></a>コメント  
 この関数によって実行可能な変換は、表に示します。  
  
|ソース|保存先|  
|------------|-----------------|  
|\<|&lt;|  
|>|&gt;|  
|&|&amp;|  
|'|&apos;|  
|"|&quot;|  
  
## <a name="getextendedchars"></a> GetExtendedChars
文字列に含まれる拡張文字の数を取得します。  
  
```  
inline int GetExtendedChars(LPCSTR szSrc, int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `szSrc`  
 分析する文字列。  
  
 `nSrcLen`  
 文字列の文字の長さ。  
  
### <a name="return-value"></a>戻り値  
 によって決定される、文字列内で見つかった拡張文字の数を返します[IsExtendedChar](#isextendedchar)です。  
  
## <a name="isextendedchar"></a> IsExtendedChar
指定された文字が拡張文字 (文字コードが 31 以下または 127 以上で、タブ、ラインフィード、キャリッジ リターン以外の文字) かどうかを判断します。  
  
```  
inline int IsExtendedChar(char ch) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *ch*  
 テストする文字  
  
### <a name="return-value"></a>戻り値  
 **TRUE**文字を拡張すると場合、 **FALSE**それ以外の場合。  
  
## <a name="qencode"></a> QEncode
"Q" エンコーディングを使用して一部のデータを変換します。  
  
```  
inline BOOL QEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCSTR pszCharSet,  
   int* pnNumEncoded = NULL) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pbSrcData`  
 エンコードするデータを保持するバッファー。  
  
 `nSrcLen`  
 エンコードするデータの長さをバイト単位で。  
  
 `szDest`  
 エンコードされたデータを受信する呼び出し元が割り当てたバッファー。  
  
 `pnDestLen`  
 文字の長さを格納する変数へのポインター`szDest`です。 関数が成功した場合、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。  
  
 `pszCharSet`  
 文字変換を使用するセットします。  
  
 *pnNumEncoded*  
 変換する必要があった安全でない文字の数を格納する変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 "Q"エンコーディング方式については、「RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt))。  
  
## <a name="qencodegetrequiredlength"></a> QEncodeGetRequiredLength 
指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。  
  
```  
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードするデータのバイト数。  
  
 `nCharsetLen`  
 変換を使用する文字セットの文字の長さ。  
  
### <a name="return-value"></a>戻り値  
 文字のエンコードされたデータを格納するバッファーのために必要な数`nSrcLen`バイトです。  
  
### <a name="remarks"></a>コメント  
 "Q"エンコーディング方式については、「RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt))。  
  
## <a name="qpdecode"></a> QPDecode
前の呼び出しによってなど quoted-printable 形式にエンコードされたデータの文字列をデコード[QPEncode](#qpencode)です。  
  
```  
inline BOOL QPDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pbSrcData`  
 デコードするデータを保持するバッファー。  
  
 [入力] `nSrcLen`  
 バイト長`pbSrcData`です。  
  
 [出力] `szDest`  
 デコードされたデータを受信する呼び出し元が割り当てたバッファー。  
  
 [出力] `pnDestLen`  
 長さのバイト数を格納する変数へのポインター`szDest`です。 関数が成功した場合、変数は、バッファーに書き込まれたバイト数を受け取ります。 関数が失敗した場合、変数は、バッファーのバイトで、必要な長さを受け取ります。  
  
 [入力] `dwFlags`  
 変換の実行方法を示すフラグ。 参照してください[ATLSMTP_QPENCODE フラグ](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4)です。  
  
### <a name="return-value"></a>戻り値  
 正常に終了した場合は、`TRUE` を返します。それ以外の場合は、`FALSE` を返します。  
  
### <a name="remarks"></a>コメント  
 引用符で囲まれた印刷可能なエンコード体系が RFC 2045 で説明されている ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt))。  
  
## <a name="qpdecodegetrequiredlength"></a> QPDecodeGetRequiredLength
quoted-printable にエンコードされた指定長の文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。  
  
```  
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードされた文字列の文字の数。  
  
### <a name="return-value"></a>戻り値  
 デコードされた文字列を格納するバッファーの必要なバイト数`nSrcLen`文字です。  
  
### <a name="remarks"></a>コメント  
 引用符で囲まれた印刷可能なエンコード体系が RFC 2045 で説明されている ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt))。  
  
## <a name="qpencode"></a> QPEncode
一部のデータを quoted-printable 形式にエンコードします。  
  
```  
inline BOOL QPEncode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pbSrcData`  
 エンコードするデータを保持するバッファー。  
  
 `nSrcLen`  
 エンコードするデータの長さをバイト単位で。  
  
 `szDest`  
 エンコードされたデータを受信する呼び出し元が割り当てたバッファー。  
  
 `pnDestLen`  
 文字の長さを格納する変数へのポインター`szDest`です。 関数が成功した場合、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。  
  
 `dwFlags`  
 変換の実行方法を記述する ATLSMTP_QPENCODE フラグ。 
- `ATLSMTP_QPENCODE_DOT` 行の先頭にピリオドが表示されている場合に、出力に追加だけでなくエンコードします。
- `ATLSMTP_QPENCODE_TRAILING_SOFT` 追加`=\r\n`エンコードされた文字列にします。

引用符で囲まれた印刷可能なエンコーディング方式については、「 [RFC 2045](http://www.ietf.org/rfc/rfc2045.txt)です。
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 引用符で囲まれた印刷可能なエンコード体系が RFC 2045 で説明されている ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt))。  
  
## <a name="qpencodegetrequiredlength"></a> QPEncodeGetRequiredLength
指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。  
  
```  
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードするデータのバイト数。  
  
### <a name="return-value"></a>戻り値  
 文字のエンコードされたデータを格納するバッファーのために必要な数`nSrcLen`バイトです。  
  
### <a name="remarks"></a>コメント  
 引用符で囲まれた印刷可能なエンコード体系が RFC 2045 で説明されている ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt))。  
  
## <a name="uudecode"></a> UUDecode
など、以前の呼び出しによって uuencode されているデータの文字列をデコード[UUEncode](#uuencode)です。  
  
```  
inline BOOL UUDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   BYTE* pbDest,  
   int* pnDestLen) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pbSrcData`  
 デコードするデータを含む文字列。  
  
 `nSrcLen`  
 バイト長`pbSrcData`です。  
  
 `pbDest`  
 デコードされたデータを受信する呼び出し元が割り当てたバッファー。  
  
 `pnDestLen`  
 長さのバイト数を格納する変数へのポインター`pbDest`です。 関数が成功した場合、変数は、バッファーに書き込まれたバイト数を受け取ります。 関数が失敗した場合、変数は、バッファーのバイトで、必要な長さを受け取ります。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 この実装は uuencoding POSIX P1003.2b/D11 仕様に従っています。  
  
## <a name="uudecodegetrequiredlength"></a> UUDecodeGetRequiredLength
指定した長さの uuencode された文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。  
  
```  
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードされた文字列の文字の数。  
  
### <a name="return-value"></a>戻り値  
 デコードされた文字列を格納するバッファーの必要なバイト数`nSrcLen`文字です。  
  
### <a name="remarks"></a>コメント  
 この実装は uuencoding POSIX P1003.2b/D11 仕様に従っています。  
  
## <a name="uuencode"></a> UUEncode
データを uuencode します。  
  
```  
inline BOOL UUEncode(  
   const BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   LPCTSTR lpszFile = _T("file"),  
   DWORD dwFlags = 0) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 `pbSrcData`  
 エンコードするデータを保持するバッファー。  
  
 `nSrcLen`  
 エンコードするデータの長さをバイト単位で。  
  
 `szDest`  
 エンコードされたデータを受信する呼び出し元が割り当てたバッファー。  
  
 `pnDestLen`  
 文字の長さを格納する変数へのポインター`szDest`です。 関数が成功した場合、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。  
  
 *プリケーション*  
 ATLSMTP_UUENCODE_HEADER がで指定した場合、ヘッダーに追加するファイル`dwFlags`です。  
  
 `dwFlags`  
 この関数の動作を制御するフラグ。 
- `ATLSMTP_UUENCODE_HEADE` ヘッダーがエンコードされます。
- `ATLSMTP_UUENCODE_END` 末尾がエンコードされます。
- `ATLSMTP_UUENCODE_DOT` データの埋め込みが行われます。  
  
### <a name="return-value"></a>戻り値  
 返します**TRUE**成功した場合、 **FALSE**エラー発生時にします。  
  
### <a name="remarks"></a>コメント  
 この実装は uuencoding POSIX P1003.2b/D11 仕様に従っています。  
  
## <a name="uuencodegetrequiredlength"></a> UUEncodeGetRequiredLength
指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。  
  
```  
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>パラメーター  
 `nSrcLen`  
 エンコードするデータのバイト数。  
  
### <a name="return-value"></a>戻り値  
 文字のエンコードされたデータを格納するバッファーのために必要な数`nSrcLen`バイトです。  
  
### <a name="remarks"></a>コメント  
 この実装は uuencoding POSIX P1003.2b/D11 仕様に従っています。  
  
### <a name="see-also"></a>関連項目  
 [概念](../../atl/active-template-library-atl-concepts.md)   
 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)   