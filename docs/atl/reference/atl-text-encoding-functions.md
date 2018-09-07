---
title: ATL テキスト エンコード関数 |Microsoft Docs
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5043b421d4ca63b22cde0f413e68b3a666a483b3
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757472"
---
# <a name="atl-text-encoding-functions"></a>ATL テキスト エンコード関数

これらの関数は、テキストのエンコードとデコードをサポートします。

|||
|-|-|
|[AtlGetHexValue](#atlgethexvalue)|16 進数の数値を取得します。|   
|[AtlGetVersion](#atlgetversion)|使用している、ATL ライブラリのバージョンを取得するには、この関数を呼び出します。  |
|[AtlHexDecode](#atlhexdecode)|以前の呼び出しで 16 進テキストとしてエンコードされたデータの文字列をデコード[AtlHexEncode](#atlhexencode)します。|
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
|[QPDecode](#qpdecode)|以前の呼び出しによってなど quoted-printable 形式でエンコードされているデータの文字列をデコード[QPEncode](#qpencode)します。|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|quoted-printable にエンコードされた指定長の文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|
|[QPEncode](#qpencode)|一部のデータを quoted-printable 形式にエンコードします。|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[UUDecode](#uudecode)|呼び出しなど、以前の呼び出しによって uuencode されているデータの文字列をデコード[UUEncode](#uuencode)します。|
|[UUDecodeGetRequiredLength](#uudecodegetrequiredlength)|指定した長さの uuencode された文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|
|[UUEncode](#uuencode)|データを uuencode します。 |
|[UUEncodeGetRequiredLength](#uuencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|

## <a name="requirements"></a>要件

**ヘッダー:** atlenc.h の関数  

## <a name="atlgethexvalue"></a> AtlGetHexValue

16 進数の数値を取得します。

```
inline char AtlGetHexValue(char chIn) throw();  
```

### <a name="parameters"></a>パラメーター

*chIn*  
16 進数の文字 '0' ~ '9'、'A'-'F' または 'a'-'f'。

### <a name="return-value"></a>戻り値

入力文字の数値の値は、16 進数として解釈されます。 たとえば、'0' の入力が 0 の値を返し、'A' の入力が 10 の値を返します。 入力文字が 16 進数でない場合は、この関数は-1 を返します。

## <a name="atlgetversion"></a> AtlGetVersion

使用している、ATL ライブラリのバージョンを取得するには、この関数を呼び出します。

```  
ATLAPI_(DWORD) AtlGetVersion(void* pReserved);  
```

### <a name="parameters"></a>パラメーター

*保持*  
予約済みのポインター。

### <a name="return-value"></a>戻り値

コンパイルまたは実行されている ATL ライブラリのバージョンの DWORD の整数値を返します。

## <a name="example"></a>例

次のように、関数を呼び出す必要があります。

[!code-cpp[NVC_ATL_Utilities#95](../../atl/codesnippet/cpp/atl-text-encoding-functions_1.cpp)]

### <a name="requirements"></a>要件

**ヘッダー:** atlbase.h  

## <a name="atlhexdecode"></a> AtlHexDecode

以前の呼び出しで 16 進テキストとしてエンコードされたデータの文字列をデコード[AtlHexEncode](#atlhexencode)します。

```    
inline BOOL AtlHexDecode(  
   LPCSTR pSrcData,  
   int nSrcLen,  
   LPBYTE pbDest,  
   int* pnDestLen) throw();  
```

### <a name="parameters"></a>パラメーター

*pSrcData*  
デコードするデータを含む文字列。

*nSrcLen*  
文字の長さ*pSrcData*します。

*pbDest*  
デコードされたデータを受信する呼び出し元が割り当てたバッファー。

*pnDestLen*  
バイト単位の長さを格納する変数を指すポインター *pbDest*します。 関数が成功すると、変数は、バッファーに書き込まれたバイト数を受け取ります。 関数が失敗した場合、変数は、バッファーのバイトで、必要な長さを受け取ります。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

## <a name="atlhexdecodegetrequiredlength"></a> AtlHexDecodeGetRequiredLength

指定した長さの 16 進エンコードされた文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。

```  
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();  
```

### <a name="parameters"></a>パラメーター

*nSrcLen*  
エンコードされた文字列内の文字の数。

### <a name="return-value"></a>戻り値

デコードされた文字列を格納するバッファーの必要なバイト数*nSrcLen*文字。

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

*pbSrcData*  
エンコードするデータを保持するバッファー。

*nSrcLen*  
エンコードするデータの長さを (バイト単位)。

*ときに szDest*  
エンコードされたデータを受信する呼び出し元が割り当てたバッファー。

*pnDestLen*  
文字の長さを格納する変数へのポインター*ときに szDest*します。 関数が成功すると、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

ソース データの各バイトは、2 つの 16 進数の文字としてエンコードされます。

## <a name="atlhexencodegetrequiredlength"></a> AtlHexEncodeGetRequiredLength

指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。

```  
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();  
```

### <a name="parameters"></a>パラメーター

*nSrcLen*  
エンコードするデータのバイト数。

### <a name="return-value"></a>戻り値

文字のエンコードされたデータを格納するバッファーのために必要な数*nSrcLen*バイト。

## <a name="atlhexvalue"></a> AtlHexValue

16 進数の数値を取得します。

```  
inline short AtlHexValue(char chIn) throw();  
```

### <a name="parameters"></a>パラメーター

*chIn*  
16 進数の文字 '0' ~ '9'、'A'-'F' または 'a'-'f'。

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
変換対象の Unicode 文字列

*nSrc*  
Unicode 文字列の文字の長さ。

*ときに szDest*  
変換後の文字列を受信する呼び出し元が割り当てたバッファー。

*nDest*  
バッファーの長さを (バイト単位)。

### <a name="return-value"></a>戻り値

変換後の文字列の文字の数を返します。

### <a name="remarks"></a>Remarks

変換後の文字列に必要なバッファーのサイズを判断するには、0 を渡すことこの関数を呼び出す*ときに szDest*と*nDest*します。

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

*pbSrcData*  
エンコードするデータを保持するバッファー。

*nSrcLen*  
エンコードするデータの長さを (バイト単位)。

*ときに szDest*  
エンコードされたデータを受信する呼び出し元が割り当てたバッファー。

*pnDestLen*  
文字の長さを格納する変数へのポインター*ときに szDest*します。 関数が成功すると、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。

*pszCharSet*  
文字変換を使用する設定。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

"B"エンコーディング スキームについては、「RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt))。

## <a name="bencodegetrequiredlength"></a> BEncodeGetRequiredLength

指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。

```  
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```

### <a name="parameters"></a>パラメーター

*nSrcLen*  
エンコードするデータのバイト数。

*nCharsetLen*  
変換に使用する文字セットの文字の数。

### <a name="return-value"></a>戻り値

文字のエンコードされたデータを格納するバッファーのために必要な数*nSrcLen*バイト。

### <a name="remarks"></a>Remarks

"B"エンコーディング スキームについては、「RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt))。

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

*szIn*  
変換対象の文字列。

*nSrclen*  
変換する文字列の文字の長さ。

*szEsc*  
変換後の文字列を受信する呼び出し元が割り当てたバッファー。

*nDestLen*  
呼び出し元が割り当てたバッファーの文字の数。

*dwFlags*  
変換の実行方法を記述する ATL_ESC フラグ。 

- ATL_ESC_FLAG_NONE の既定の動作です。 引用符に、アポストロフィは変換されません。
- 引用符で囲む ATL_ESC_FLAG_ATTR マークおよびアポストロフィに変換されます`&quot;`と`&apos;`それぞれします。

### <a name="return-value"></a>戻り値

変換された文字列の文字の数。

### <a name="remarks"></a>Remarks

この関数によって実行可能な変換は、表に示した。

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

*szSrc*  
分析する文字列。

*nSrcLen*  
文字列の文字の長さ。

### <a name="return-value"></a>戻り値

によって決定される文字列内で見つかった拡張文字の数を返します[IsExtendedChar](#isextendedchar)します。

## <a name="isextendedchar"></a> IsExtendedChar

指定された文字が拡張文字 (文字コードが 31 以下または 127 以上で、タブ、ラインフィード、キャリッジ リターン以外の文字) かどうかを判断します。

```  
inline int IsExtendedChar(char ch) throw();  
```

### <a name="parameters"></a>パラメーター

*ch*  
テストする文字

### <a name="return-value"></a>戻り値

文字拡張されている場合、FALSE それ以外の場合は TRUE。

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

*pbSrcData*  
エンコードするデータを保持するバッファー。

*nSrcLen*  
エンコードするデータの長さを (バイト単位)。

*ときに szDest*  
エンコードされたデータを受信する呼び出し元が割り当てたバッファー。

*pnDestLen*  
文字の長さを格納する変数へのポインター*ときに szDest*します。 関数が成功すると、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。

*pszCharSet*  
文字変換を使用する設定。

*pnNumEncoded*  
変換する必要があった安全でない文字の数を格納する変数へのポインター。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

"Q"エンコーディング スキームについては、「RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt))。

## <a name="qencodegetrequiredlength"></a> QEncodeGetRequiredLength

指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。

```  
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```

### <a name="parameters"></a>パラメーター

*nSrcLen*  
エンコードするデータのバイト数。

*nCharsetLen*  
変換に使用する文字セットの文字の数。

### <a name="return-value"></a>戻り値

文字のエンコードされたデータを格納するバッファーのために必要な数*nSrcLen*バイト。

### <a name="remarks"></a>Remarks

"Q"エンコーディング スキームについては、「RFC 2047 ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt))。

## <a name="qpdecode"></a> QPDecode

以前の呼び出しによってなど quoted-printable 形式でエンコードされているデータの文字列をデコード[QPEncode](#qpencode)します。

```  
inline BOOL QPDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw();  
```

### <a name="parameters"></a>パラメーター

[in]*pbSrcData*  
デコードするデータを保持するバッファー。

[in]*nSrcLen*  
バイト長*pbSrcData*します。

[out]*ときに szDest*  
デコードされたデータを受信する呼び出し元が割り当てたバッファー。

[out]*pnDestLen*  
バイト単位の長さを格納する変数を指すポインター*ときに szDest*します。 関数が成功すると、変数は、バッファーに書き込まれたバイト数を受け取ります。 関数が失敗した場合、変数は、バッファーのバイトで、必要な長さを受け取ります。

[in]*dwFlags*  
変換の実行方法を記述する ATLSMTP_QPENCODE フラグ。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

引用符で囲まれた印刷可能なエンコード体系が RFC 2045 で説明されている ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt))。

## <a name="qpdecodegetrequiredlength"></a> QPDecodeGetRequiredLength

quoted-printable にエンコードされた指定長の文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。

```  
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();  
```

### <a name="parameters"></a>パラメーター

*nSrcLen*  
エンコードされた文字列内の文字の数。

### <a name="return-value"></a>戻り値

デコードされた文字列を格納するバッファーの必要なバイト数*nSrcLen*文字。

### <a name="remarks"></a>Remarks

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

*pbSrcData*  
エンコードするデータを保持するバッファー。

*nSrcLen*  
エンコードするデータの長さを (バイト単位)。

*ときに szDest*  
エンコードされたデータを受信する呼び出し元が割り当てたバッファー。

*pnDestLen*  
文字の長さを格納する変数へのポインター*ときに szDest*します。 関数が成功すると、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。

*dwFlags*  
変換の実行方法を記述する ATLSMTP_QPENCODE フラグ。 
- ATLSMTP_QPENCODE_DOT 場合、行の先頭にピリオドが表示されます、これは、出力に追加だけでなくエンコードします。
- ATLSMTP_QPENCODE_TRAILING_SOFT 追加`=\r\n`エンコードされた文字列にします。

引用符で囲まれた印刷可能なエンコード スキームについては、「 [RFC 2045](http://www.ietf.org/rfc/rfc2045.txt)します。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

引用符で囲まれた印刷可能なエンコード体系が RFC 2045 で説明されている ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt))。

## <a name="qpencodegetrequiredlength"></a> QPEncodeGetRequiredLength

指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。

```  
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();  
```

### <a name="parameters"></a>パラメーター

*nSrcLen*  
エンコードするデータのバイト数。

### <a name="return-value"></a>戻り値

文字のエンコードされたデータを格納するバッファーのために必要な数*nSrcLen*バイト。

### <a name="remarks"></a>Remarks

引用符で囲まれた印刷可能なエンコード体系が RFC 2045 で説明されている ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt))。

## <a name="uudecode"></a> UUDecode

呼び出しなど、以前の呼び出しによって uuencode されているデータの文字列をデコード[UUEncode](#uuencode)します。

```  
inline BOOL UUDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   BYTE* pbDest,  
   int* pnDestLen) throw ();  
```

### <a name="parameters"></a>パラメーター

*pbSrcData*  
デコードするデータを含む文字列。

*nSrcLen*  
バイト長*pbSrcData*します。

*pbDest*  
デコードされたデータを受信する呼び出し元が割り当てたバッファー。

*pnDestLen*  
バイト単位の長さを格納する変数を指すポインター *pbDest*します。 関数が成功すると、変数は、バッファーに書き込まれたバイト数を受け取ります。 関数が失敗した場合、変数は、バッファーのバイトで、必要な長さを受け取ります。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

この実装は uuencoding POSIX P1003.2b/D11 仕様に従っています。

## <a name="uudecodegetrequiredlength"></a> UUDecodeGetRequiredLength

指定した長さの uuencode された文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。

```  
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();  
```

### <a name="parameters"></a>パラメーター

*nSrcLen*  
エンコードされた文字列内の文字の数。

### <a name="return-value"></a>戻り値

デコードされた文字列を格納するバッファーの必要なバイト数*nSrcLen*文字。

### <a name="remarks"></a>Remarks

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

*pbSrcData*  
エンコードするデータを保持するバッファー。

*nSrcLen*  
エンコードするデータの長さを (バイト単位)。

*ときに szDest*  
エンコードされたデータを受信する呼び出し元が割り当てたバッファー。

*pnDestLen*  
文字の長さを格納する変数へのポインター*ときに szDest*します。 関数が成功すると、変数は、バッファーに書き込まれた文字数を受け取ります。 関数が失敗した場合、変数は、バッファーの文字で、必要な長さを受け取ります。

*プリケーション*  
ATLSMTP_UUENCODE_HEADER がで指定した場合、ヘッダーに追加するファイル*dwFlags*します。

*dwFlags*  
この関数の動作を制御するフラグ。 
- ATLSMTP_UUENCODE_HEADE ヘッダーがエンコードされます。
- ATLSMTP_UUENCODE_END 末尾がエンコードされます。
- ATLSMTP_UUENCODE_DOT データの埋め込みが行われます。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

この実装は uuencoding POSIX P1003.2b/D11 仕様に従っています。

## <a name="uuencodegetrequiredlength"></a> UUEncodeGetRequiredLength

指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。

```  
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();  
```

### <a name="parameters"></a>パラメーター

*nSrcLen*  
エンコードするデータのバイト数。

### <a name="return-value"></a>戻り値

文字のエンコードされたデータを格納するバッファーのために必要な数*nSrcLen*バイト。

### <a name="remarks"></a>Remarks

この実装は uuencoding POSIX P1003.2b/D11 仕様に従っています。

### <a name="see-also"></a>関連項目

[概念](../../atl/active-template-library-atl-concepts.md)   
[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)   