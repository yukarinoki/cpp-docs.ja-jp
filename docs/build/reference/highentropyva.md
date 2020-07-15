---
title: /HIGHENTROPYVA
ms.date: 06/12/2018
f1_keywords:
- /HIGHENTROPYVA
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
ms.openlocfilehash: b2ff9929de74d99fbc45e4f4ff38fd6b939697bc
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373828"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

実行可能ファイル イメージが高いエントロピの 64 ビット ASLR (Address Space Layout Randomization) をサポートするかどうかを指定します。

## <a name="syntax"></a>構文

> **/HIGHENTROPYVA**[**: NO**]

## <a name="remarks"></a>解説

このオプションは、64ビットのアドレスを持つ ASLR がサポートされているかどうかを示すために、*実行可能イメージ*(.dll ファイルまたは .exe ファイル) のヘッダーを変更します。 このオプションを実行可能ファイルおよび依存するモジュールのすべてに設定すると、64 ビット ASLR をサポートするオペレーティング システムは、読み込み時に 64 ビットの仮想アドレス空間でランダム化されたアドレスを使用して、実行可能イメージのセグメントのベース アドレスをリベースできます。 この大きいアドレス空間により、攻撃者は特定のメモリ領域の位置を推測することが困難となります。

既定では、リンカーは64ビットの実行可能イメージに対して **/HIGHENTROPYVA**を有効にします。 このオプションには[/LARGEADDRESSAWARE](largeaddressaware.md)が必要です。これは64ビットイメージでも既定で有効になっています。 **/HIGHENTROPYVA**は、32ビットの実行可能イメージには適用されません。このオプションは無視されます。 このオプションを明示的に無効にするには、 **/HIGHENTROPYVA: NO**を使用します。 このオプションを有効にするには、 [/DYNAMICBASE](dynamicbase.md)オプションも設定する必要があります。

## <a name="see-also"></a>関連項目

- [EDITBIN オプション](editbin-options.md)
- [/DYNAMICBASE](dynamicbase.md)
- [Windows ISV ソフトウェアセキュリティ防御](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
