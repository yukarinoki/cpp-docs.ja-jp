---
title: ATL のエンコーディングのリファレンス
ms.date: 11/04/2016
helpviewer_keywords:
- encoding
- encoding, functions
ms.assetid: 82d4fdf3-3c4a-4fe2-b297-8ffb4714406f
ms.openlocfilehash: 8fe0506980c22ad9a64bf69f6877b041b957a1a4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295722"
---
# <a name="atl-encoding-reference"></a>ATL のエンコーディングのリファレンス

Atlenc.h の関数のコードでは、uuencode、16 進数などの一般的なインターネット標準の範囲と UTF8 でエンコードがサポートされています。

### <a name="functions"></a>関数

|||
|-|-|
|[AtlGetHexValue](reference/atl-text-encoding-functions.md#atlgethexvalue)|16 進数の数値を取得します。|
|[AtlHexDecode](reference/atl-text-encoding-functions.md#atlhexdecode)|以前の呼び出しで 16 進テキストとしてエンコードされたデータの文字列をデコード[AtlHexEncode](reference/atl-text-encoding-functions.md#atlhexencode)します。|
|[AtlHexDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#atlhexdecodegetrequiredlength)|指定した長さの 16 進エンコードされた文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|
|[AtlHexEncode](reference/atl-text-encoding-functions.md#atlhexencode)|一部のデータを 16 進テキストの文字列としてエンコードします。|
|[AtlHexEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#atlhexencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[AtlUnicodeToUTF8](reference/atl-text-encoding-functions.md#atlunicodetoutf8)|Unicode 文字列を UTF-8 に変換します。|
|[BEncode](reference/atl-text-encoding-functions.md#bencode)|"B" エンコーディングを使用して一部のデータを変換します。|
|[BEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#bencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[EscapeXML](reference/atl-text-encoding-functions.md#escapexml)|XML での使用には安全でない文字を安全な文字に変換します。|
|[GetExtendedChars](reference/atl-text-encoding-functions.md#getextendedchars)|文字列に含まれる拡張文字の数を取得します。|
|[IsExtendedChar](reference/atl-text-encoding-functions.md#isextendedchar)|指定された文字が拡張文字 (文字コードが 31 以下または 127 以上で、タブ、ラインフィード、キャリッジ リターン以外の文字) かどうかを判断します。|
|[QEncode](reference/atl-text-encoding-functions.md#qencode)|"Q" エンコーディングを使用して一部のデータを変換します。|
|[QEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[QPDecode](reference/atl-text-encoding-functions.md#qpdecode)|以前の呼び出しによってなど quoted-printable 形式でエンコードされているデータの文字列をデコード[QPEncode](reference/atl-text-encoding-functions.md#qpencode)します。|
|[QPDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpdecodegetrequiredlength)|quoted-printable にエンコードされた指定長の文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|
|[QPEncode](reference/atl-text-encoding-functions.md#qpencode)|一部のデータを quoted-printable 形式にエンコードします。|
|[QPEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|
|[UUDecode](reference/atl-text-encoding-functions.md#uudecode)|呼び出しなど、以前の呼び出しによって uuencode されているデータの文字列をデコード[UUEncode](reference/atl-text-encoding-functions.md#uuencode)します。|
|[UUDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#uudecodegetrequiredlength)|指定した長さの uuencode された文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|
|[UUEncode](reference/atl-text-encoding-functions.md#uuencode)|データを uuencode します。|
|[UUEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#uuencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM デスクトップ コンポーネント](../atl/atl-com-desktop-components.md)
