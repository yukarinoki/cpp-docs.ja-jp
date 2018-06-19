---
title: レジスタの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ce58e2cf-afd3-4068-980e-28a209298265
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c77469a8cef03827101f4bf367c00a3bb440820
ms.sourcegitcommit: 4fc6869067d533b175207befd2dc60346afee285
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34225220"
---
# <a name="register-usage"></a>レジスタの使用

浮動小数点の使用可能なアーキテクチャでは、16 個の XMM/YMM と同様に 16 個の汎用レジスタ (呼ぶ整数レジスタと)、x64 を登録します。 volatile レジスタは、呼び出しで使用された後に内容が破棄されることが、呼び出し元によって想定されているスクラッチ レジスタです。 関数呼び出しで使用された後もレジスタの値を保持するには非 volatile レジスタが必要です。使用された非 volatile レジスタの保存は、呼び出し先が行う必要があります。

## <a name="register-volatility-and-preservation"></a>登録の更新頻度と保持

関数呼び出しで各レジスタがどのように使用されるかを次の表に示します。

||||
|-|-|-|
|登録|状態|用途|
|RAX|Volatile|戻り値レジスタ|
|RCX|Volatile|1 番目の整数引数|
|RDX|Volatile|2 番目の整数引数|
|R8|Volatile|3 番目の整数引数|
|R9|Volatile|4 番目の整数引数|
|R10:R11|Volatile|必要に応じて、呼び出し元によって保持される必要があります。syscall/sysret 命令で使用されます。|
|R12:R15|非 volatile|呼び出し先によって保持される必要があります。|
|RDI|非 volatile|呼び出し先によって保持される必要があります。|
|RSI|非 volatile|呼び出し先によって保持される必要があります。|
|RBX|非 volatile|呼び出し先によって保持される必要があります。|
|RBP|非 volatile|フレーム ポインターとして使用できます。呼び出し先によって保持される必要があります。|
|RSP|非 volatile|スタック ポインター|
|XMM0, YMM0|Volatile|1 番目の FP 引数。`__vectorcall` が使用された場合の 1 番目のベクター型引数。|
|XMM1, YMM1|Volatile|2 番目の FP 引数。`__vectorcall` が使用された場合の 2 番目のベクター型引数。|
|XMM2, YMM2|Volatile|3 番目の FP 引数。`__vectorcall` が使用された場合の 3 番目のベクター型引数。|
|XMM3, YMM3|Volatile|4 番目の FP 引数。`__vectorcall` が使用された場合の 4 番目のベクター型引数。|
|XMM4, YMM4|Volatile|必要に応じて、呼び出し元によって保持される必要があります。`__vectorcall` が使用された場合の 5 番目のベクター型引数。|
|XMM5, YMM5|Volatile|必要に応じて、呼び出し元によって保持される必要があります。`__vectorcall` が使用された場合の 6 番目のベクター型引数。|
|XMM6:XMM15, YMM6:YMM15|非 volatile (XMM)、volatile (YMM の上半分)|呼び出し先によって保持される必要があります。 必要に応じて、呼び出し元によって YMM レジスタが保持される必要があります。|

関数の終了と C ランタイム ライブラリの呼び出しおよび Windows システムの呼び出しに関数のエントリは、CPU の方向フラグをクリアするフラグの登録が必要です。

## <a name="see-also"></a>関連項目

- [x64 ソフトウェア規約](../build/x64-software-conventions.md)
- [__vectorcall](../cpp/vectorcall.md)
- [方向フラグ](../c-runtime-library/direction-flag.md)
