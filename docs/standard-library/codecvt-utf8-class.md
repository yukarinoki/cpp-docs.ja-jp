---
description: '詳細については、次を参照してください: codecvt_utf8'
title: codecvt_utf8
ms.date: 11/04/2016
f1_keywords:
- codecvt/std::codecvt_utf8
helpviewer_keywords:
- codecvt_utf8 class
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
ms.openlocfilehash: b0da37607d563786285564d17b2c8a49e9e064bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234034"
---
# <a name="codecvt_utf8"></a>codecvt_utf8

UCS 2 または UCS 4 としてエンコードされたワイド文字と、UTF-8 としてエンコードされたバイトストリームを変換する [ロケール](../standard-library/locale-class.md) ファセットを表します。

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>パラメーター

*Elem*\
ワイド文字要素型。

*Maxcode*\
ロケール ファセットの文字の最大数。

*Mode*\
ロケール ファセットの構成情報。

## <a name="remarks"></a>解説

このバイト ストリームはバイナリ ファイルまたはテキスト ファイルに書き込むことができます。

## <a name="requirements"></a>要件

ヘッダー: \<codecvt>

名前空間: std
