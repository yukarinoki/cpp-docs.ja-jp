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
ms.openlocfilehash: aa4147f28e7b780e9d916526f0e46e91432fd1ce
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714234"
---
# <a name="codecvtutf16"></a>codecvt_utf16

UCS-2 または UCS-4 としてエンコードされたワイド文字と、UTF-16LE または UTF-16BE としてエンコードされたバイト ストリームを変換する[ロケール](../standard-library/locale-class.md) ファセットを表します。

```cpp
template<class Elem, unsigned long Maxcode = 0x10ffff, codecvt_mode Mode = (codecvt_mode)0>
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>
```

## <a name="parameters"></a>パラメーター

*Elem*<br/>
ワイド文字要素型。

*Maxcode*<br/>
ロケール ファセットの文字の最大数。

*モード*<br/>
ロケール ファセットの構成情報。

## <a name="remarks"></a>Remarks

このテンプレート クラスでは、UCS-2 または UCS-4 としてエンコードされたワイド文字と、UTF-16LE (Mode と little_endian の場合) または UTF-16BE (その他の場合) としてエンコードされたバイト ストリームを変換します。

このバイト ストリームはバイナリ ファイルに書き込む必要があります。テキスト ファイルに書き込むと、破損する場合があります。

## <a name="requirements"></a>要件

ヘッダー: \<codecvt >

Namespace: std