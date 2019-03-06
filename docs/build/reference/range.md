---
title: /RANGE
ms.date: 11/04/2016
f1_keywords:
- /RANGE
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
ms.openlocfilehash: 011a8f9b2c8d0722e9aff98d52bb47dc549cc769
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421637"
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
