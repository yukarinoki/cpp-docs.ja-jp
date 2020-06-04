---
title: 浮動小数点値のアンダーフロー
ms.date: 11/04/2016
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
ms.openlocfilehash: 93230b50b81ede44a9c55406db1566df2660c1ba
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344060"
---
# <a name="underflow-of-floating-point-values"></a>浮動小数点値のアンダーフロー

**ANSI 4.5.1** 数値演算関数がアンダーフロー エラー時に、整数式 `errno` を `ERANGE` マクロの値に設定するかどうか

浮動小数点アンダーフローは、式 `errno` を `ERANGE` に設定しません。 値がゼロに近づき、最終的にアンダーフローすると、値はゼロに設定されます。

## <a name="see-also"></a>関連項目

[ライブラリ関数](../c-language/library-functions.md)
