---
description: '詳細情報: 遅延読み込みに必要な値の計算'
title: 遅延読み込みに必要な値を計算します
ms.date: 01/19/2021
helpviewer_keywords:
- helper functions, calculating necessary values
ms.openlocfilehash: ae5e0c15b5b13f12fd90c1378a1e449516b55f43
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667442"
---
# <a name="calculate-necessary-values-for-delay-loading"></a>遅延読み込みに必要な値を計算します

遅延読み込みヘルパールーチンでは、2つの重要な情報を計算する必要があります。 では、 *`delayhlp.cpp`* この情報を計算するためにのインライン関数が2つあります。

- 1つ目のは、 `IndexFromPImgThunkData` 現在のインポートのインデックスを3つの異なるテーブル (インポートアドレステーブル (IAT)、バインドされたインポートアドレステーブル (BIAT)、およびバインドされていないインポートアドレステーブル (UIAT)) に計算します。

- 2番目のは、 `CountOfImports` 有効な IAT 内のインポートの数をカウントします。

```C
// utility function for calculating the index of the current import
// for all the tables (INT, BIAT, UIAT, and IAT).
__inline unsigned
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {
    return pitdCur - pitdBase;
    }

// utility function for calculating the count of imports given the base
// of the IAT. NB: this only works on a valid IAT!
__inline unsigned
CountOfImports(PCImgThunkData pitdBase) {
    unsigned        cRet = 0;
    PCImgThunkData  pitd = pitdBase;
    while (pitd->u1.Function) {
        pitd++;
        cRet++;
        }
    return cRet;
    }
```

## <a name="see-also"></a>こちらもご覧ください

[ヘルパー関数について](understanding-the-helper-function.md)
