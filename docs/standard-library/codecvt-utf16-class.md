---
title: codecvt_utf16
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf16
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
ms.openlocfilehash: 73177985727f4da5cf3ca4eb9e3cc3fb5976f76d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215281"
---
# <a name="codecvt_utf16"></a>codecvt_utf16

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

*モード*\
ロケール ファセットの構成情報。

## <a name="remarks"></a>解説

このクラステンプレートは、UCS 2 または UCS 4 としてエンコードされたワイド文字と、16LE としてエンコードされたバイトストリーム (モード & little_endian の場合は utf-16、それ以外の場合は utf-16 に変換します。

このバイト ストリームはバイナリ ファイルに書き込む必要があります。テキスト ファイルに書き込むと、破損する場合があります。

## <a name="requirements"></a>必要条件

ヘッダー: \<codecvt >

名前空間: std
