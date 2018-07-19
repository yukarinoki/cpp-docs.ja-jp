---
title: codecvt_utf16 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_utf16
dev_langs:
- C++
helpviewer_keywords:
- codecvt_utf16 class
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdfcf3c6a562f7aab0164e3d63d468ba39ec0023
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954100"
---
# <a name="codecvtutf16"></a>codecvt_utf16

UCS-2 または UCS-4 としてエンコードされたワイド文字と、UTF-16LE または UTF-16BE としてエンコードされたバイト ストリームを変換する[ロケール](../standard-library/locale-class.md) ファセットを表します。

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>パラメーター

*Elem*ワイド文字要素の型。
*Maxcode*ロケール ファセットの文字の最大数。
*モード*ロケール ファセットの構成情報。

## <a name="remarks"></a>Remarks

このテンプレート クラスでは、UCS-2 または UCS-4 としてエンコードされたワイド文字と、UTF-16LE (Mode と little_endian の場合) または UTF-16BE (その他の場合) としてエンコードされたバイト ストリームを変換します。

このバイト ストリームはバイナリ ファイルに書き込む必要があります。テキスト ファイルに書き込むと、破損する場合があります。

## <a name="requirements"></a>必要条件

ヘッダー: \<codecvt> 名前空間: std