---
title: 予約語
ms.date: 11/04/2016
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
ms.openlocfilehash: 62893d4af1633bc2c89d2d6a0fa71309a0411ad5
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836843"
---
# <a name="reserved-words"></a>予約語

次の単語は、リンカーによって予約されています。 これらの名前は、名前が二重引用符 ("") で囲まれている場合にのみ、 [モジュール定義ステートメント](module-definition-dot-def-files.md) の引数として使用できます。

:::row:::
   :::column span="":::
      **`APPLOADER`**<sup>1</sup>\
      **`BASE`**\
      **`CODE`**\
      **`CONFORMING`**\
      **`DATA`**\
      **`DESCRIPTION`**\
      **`DEV386`**\
      **`DISCARDABLE`**\
      **`DYNAMIC`**\
      **`EXECUTE-ONLY`**\
      **`EXECUTEONLY`**\
      **`EXECUTEREAD`**\
      **`EXETYPE`**\
      **`EXPORTS`**\
      **`FIXED`** <sup>1</sup>
   :::column-end:::
   :::column span="":::
      **`FUNCTIONS`**<sup>3</sup>\
      **`HEAPSIZE`**\
      **`IMPORTS`**\
      **`IMPURE`**<sup>1</sup>\
      **`INCLUDE`**<sup>3</sup>\
      **`INITINSTANCE`**<sup>3</sup>\
      **`IOPL`**\
      **`LIBRARY`**<sup>1</sup>\
      **`LOADONCALL`**<sup>1</sup>\
      **`LONGNAMES`**<sup>3</sup>\
      **`MOVABLE`**<sup>1</sup>\
      **`MOVEABLE`**<sup>1</sup>\
      **`MULTIPLE`**\
      **`NAME`**\
      **`NEWFILES`** <sup>2</sup>
   :::column-end:::
   :::column span="":::
      **`NODATA`**<sup>1</sup>\
      **`NOIOPL`**<sup>1</sup>\
      **`NONAME`**\
      **`NONCONFORMING`**<sup>1</sup>\
      **`NONDISCARDABLE`**\
      **`NONE`**\
      **`NONSHARED`**\
      **`NOTWINDOWCOMPAT`**<sup>1</sup>\
      **`OBJECTS`**\
      **`OLD`**<sup>1</sup>\
      **`PRELOAD`**\
      **`PRIVATE`**\
      **`PROTMODE`**<sup>3</sup>\
      **`PURE`**<sup>1</sup>\
      **`READONLY`**
   :::column-end:::
   :::column span="":::
      **`READWRITE`**\
      **`REALMODE`**<sup>1</sup>\
      **`RESIDENT`**\
      **`RESIDENTNAME`**<sup>1</sup>\
      **`SECTIONS`**\
      **`SEGMENTS`**\
      **`SHARED`**\
      **`SINGLE`**\
      **`STACKSIZE`**\
      **`STUB`**\
      **`VERSION`**\
      **`WINDOWAPI`**\
      **`WINDOWCOMPAT`**\
      **`WINDOWS`**
   :::column-end:::
:::row-end:::

<sup>1</sup> リンカーは、この用語が検出されたときに警告 ("無視") を出力します。 ただし、この単語は予約されたままです。

<sup>2</sup> リンカーはこの単語を無視しますが、警告は出力しません。

## <a name="see-also"></a>関連項目

- [MSVC リンカーのリファレンス](linking.md)
- [MSVC リンカー オプション](linker-options.md)
