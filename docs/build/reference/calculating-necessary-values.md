---
description: '詳細情報: 必要な値の計算'
title: 必要な値の計算
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions, calculating necessary values
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
ms.openlocfilehash: 92d8462be2db55dbc10375629b133d9286560878
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179344"
---
# <a name="calculating-necessary-values"></a>必要な値の計算

2つの重要な情報は、遅延ヘルパールーチンによって計算される必要があります。 そのために、この情報を計算するための2つのインライン関数が delayhlp にあります。

- 最初のは、現在のインポートのインデックスを3つの異なるテーブル (インポートアドレステーブル (IAT)、バインドされたインポートアドレステーブル (BIAT)、およびバインドされていないインポートアドレステーブル (UIAT)) に計算します。

- 2番目の値は、有効な IAT 内のインポートの数をカウントします。

```cpp
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

## <a name="see-also"></a>関連項目

[ヘルパー関数について](understanding-the-helper-function.md)
