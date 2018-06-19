---
title: ATL のエンコーディングのリファレンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- encoding
- encoding, functions
ms.assetid: 82d4fdf3-3c4a-4fe2-b297-8ffb4714406f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d8cbb23c390a47b1bbfb7b1a78b327f07b06869
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358629"
---
# <a name="atl-encoding-reference"></a>ATL のエンコーディングのリファレンス
Uuencode、16 進数などの一般的なインターネット標準の範囲および UTF8 でエンコードすると、atlenc.h のコードでサポートされます。  
  
### <a name="functions"></a>関数  
  
|||  
|-|-|  
|[AtlGetHexValue](reference/atl-text-encoding-functions.md#atlgethexvalue)|16 進数の数値を取得します。|  
|[AtlHexDecode](reference/atl-text-encoding-functions.md#atlhexdecode)|前の呼び出しによって 16 進テキストとしてエンコードされているデータの文字列をデコード[AtlHexEncode](reference/atl-text-encoding-functions.md#atlhexencode)です。|  
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
|[QPDecode](reference/atl-text-encoding-functions.md#qpdecode)|前の呼び出しによってなど quoted-printable 形式にエンコードされたデータの文字列をデコード[QPEncode](reference/atl-text-encoding-functions.md#qpencode)です。|  
|[QPDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpdecodegetrequiredlength)|quoted-printable にエンコードされた指定長の文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|  
|[QPEncode](reference/atl-text-encoding-functions.md#qpencode)|一部のデータを quoted-printable 形式にエンコードします。|  
|[QPEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|  
|[UUDecode](reference/atl-text-encoding-functions.md#uudecode)|など、以前の呼び出しによって uuencode されているデータの文字列をデコード[UUEncode](reference/atl-text-encoding-functions.md#uuencode)です。|  
|[UUDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#uudecodegetrequiredlength)|指定した長さの uuencode された文字列からデコードされたデータを格納できるバッファーのサイズを、バイト単位で取得します。|  
|[UUEncode](reference/atl-text-encoding-functions.md#uuencode)|データを uuencode します。|  
|[UUEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#uuencodegetrequiredlength)|指定したサイズのデータからエンコードされた文字列を格納できるバッファーのサイズを、文字数で取得します。|  
  
## <a name="see-also"></a>関連項目  
 [概念](../atl/active-template-library-atl-concepts.md)   
 [ATL COM デスクトップ コンポーネント](../atl/atl-com-desktop-components.md)

