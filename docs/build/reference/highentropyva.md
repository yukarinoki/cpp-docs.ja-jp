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
ms.openlocfilehash: 1adc12c0673764460b4af5eb7cf3b394d9666e81
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404101"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

実行可能ファイル イメージが高いエントロピの 64 ビット ASLR (Address Space Layout Randomization) をサポートするかどうかを指定します。

## <a name="syntax"></a>構文

> **`/HIGHENTROPYVA`**[**`:NO`**]

## <a name="remarks"></a>解説

このオプションは、 *executable image* *`.dll`* *`.exe`* 64 ビットのアドレス ASLR のサポートを示すために、実行可能イメージファイル (たとえば、ファイルやファイル) のヘッダーを変更します。 効果を与えるには、実行可能ファイルと、それが依存するすべてのモジュールに対してオプションを設定します。 その後、64ビット ASLR をサポートするオペレーティングシステムは、ランダム化された64ビットの仮想アドレスを使用して、読み込み時に実行可能イメージのセグメントをリベースできます。 この大きいアドレス空間により、攻撃者は特定のメモリ領域の位置を推測することが困難となります。

既定では、リンカーは **`/HIGHENTROPYVA`** 64 ビットの実行可能イメージを有効にします。 このオプションには、との両方が必要です [`/DYNAMICBASE`](dynamicbase.md) [`/LARGEADDRESSAWARE`](largeaddressaware.md) 。これは、64ビットイメージに対しても既定で有効になっています。 **`/HIGHENTROPYVA`** 32ビットの実行可能イメージには適用できません。オプションは無視されます。 このオプションを明示的に無効にするには、を使用し **`/HIGHENTROPYVA:NO`** ます。

## <a name="see-also"></a>関連項目

[EDITBIN オプション](editbin-options.md)\
[`/DYNAMICBASE`](dynamicbase.md)\
[`/LARGEADDRESSAWARE`](largeaddressaware.md)\
[Windows ISV ソフトウェアセキュリティ防御](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
