---
description: 詳細情報:/範囲
title: /RANGE
ms.date: 11/04/2016
f1_keywords:
- /RANGE
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
ms.openlocfilehash: 9af54bddde977e92b5256f0835c31afbff1405d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225402"
---
# <a name="range"></a>/RANGE

/RAWDATA や/DISASM. など、他の dumpbin オプションと共に使用した場合の dumpbin の出力を変更します。

## <a name="syntax"></a>構文

```
/RANGE:vaMin[,vaMax]
```

## <a name="parameters"></a>パラメーター

*vaMin*<br/>
Dumpbin 操作を開始する仮想アドレス。

*vaMax*<br/>
OptionalDumpbin 操作を終了する仮想アドレス。 指定しない場合、dumpbin はファイルの末尾に移ります。

## <a name="remarks"></a>解説

イメージの仮想アドレスを表示するには、イメージのマップファイル (RVA + Base)、dumpbin の **/disasm** または **/HEADERS** オプション、または Visual Studio デバッガーの [逆アセンブリ] ウィンドウを使用します。

## <a name="example"></a>例

この例では、/ **範囲** を使用して、 **/disasm** オプションの表示を変更します。 この例では、開始値は10進数として表され、終了値は16進数として指定されます。

```
dumpbin /disasm /range:4219334,0x004061CD t.exe
```

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](dumpbin-options.md)
