---
title: -範囲は |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /RANGE
dev_langs:
- C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47e7525b8c1872616182141d624bff8f94571952
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712193"
---
# <a name="range"></a>/RANGE

Dumpbin/RAWDATA または/DISASM など、他の dumpbin オプションと共に使用する場合の出力を変更します。

## <a name="syntax"></a>構文

```
/RANGE:vaMin[,vaMax]
```

## <a name="parameters"></a>パラメーター

*vaMin*<br/>
Dumpbin 操作を開始する仮想アドレス。

*vaMax*<br/>
(省略可能)Dumpbin 操作が終了するたい仮想アドレス。 指定しない場合、dumpbin は、ファイルの末尾に移動します。

## <a name="remarks"></a>Remarks

イメージの仮想アドレスを表示するイメージ (RVA + ベース) のマップ ファイルを使用して、 **/DISASM**または **/HEADERS** dumpbin、または Visual Studio デバッガーで逆アセンブル ウィンドウのオプション。

## <a name="example"></a>例

この例で**範囲/** の表示を変更するために使用、 **/disasm**オプション。 この例では、開始値は 10 進数として表現し、終了値は 16 進数として指定します。

```
dumpbin /disasm /range:4219334,0x004061CD t.exe
```

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)