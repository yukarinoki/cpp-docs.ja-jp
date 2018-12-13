---
title: 浮動小数点値のアンダーフロー
ms.date: 11/04/2016
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
ms.openlocfilehash: cd4aadc5ab006b79a43e31348fa101d40e8ca03a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477364"
---
# <a name="underflow-of-floating-point-values"></a>浮動小数点値のアンダーフロー

**ANSI 4.5.1** 数値演算関数がアンダーフロー エラー時に、整数式 `errno` を `ERANGE` マクロの値に設定するかどうか

浮動小数点アンダーフローは、式 `errno` を `ERANGE` に設定しません。 値がゼロに近づき、最終的にアンダーフローすると、値はゼロに設定されます。

## <a name="see-also"></a>参照

[ライブラリ関数](../c-language/library-functions.md)