---
title: codecvt_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf16
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
ms.openlocfilehash: ca66a3273567a8d30a982211a6e977c129b00f5f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459709"
---
# <a name="codecvtutf16"></a>codecvt_utf16

UCS-2 または UCS-4 としてエンコードされたワイド文字と、UTF-16LE または UTF-16BE としてエンコードされたバイト ストリームを変換する[ロケール](../standard-library/locale-class.md) ファセットを表します。

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>パラメーター

*Elem*\
ワイド文字要素型。

*Maxcode*\
ロケール ファセットの文字の最大数。

*Mode*\
ロケール ファセットの構成情報。

## <a name="remarks"></a>Remarks

このテンプレート クラスでは、UCS-2 または UCS-4 としてエンコードされたワイド文字と、UTF-16LE (Mode と little_endian の場合) または UTF-16BE (その他の場合) としてエンコードされたバイト ストリームを変換します。

このバイト ストリームはバイナリ ファイルに書き込む必要があります。テキスト ファイルに書き込むと、破損する場合があります。

## <a name="requirements"></a>必要条件

ヘッダー: \<codecvt >

名前空間: std