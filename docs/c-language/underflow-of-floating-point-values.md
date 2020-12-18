---
description: '詳細情報: 浮動小数点値のアンダーフロー'
title: 浮動小数点値のアンダーフロー
ms.date: 11/04/2016
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
ms.openlocfilehash: 3d8ddd665aa33e1c47f9f187f759058501bc5484
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321298"
---
# <a name="underflow-of-floating-point-values"></a>浮動小数点値のアンダーフロー

**ANSI 4.5.1** 数値演算関数がアンダーフロー エラー時に、整数式 `errno` を `ERANGE` マクロの値に設定するかどうか

浮動小数点アンダーフローは、式 `errno` を `ERANGE` に設定しません。 値がゼロに近づき、最終的にアンダーフローすると、値はゼロに設定されます。

## <a name="see-also"></a>関連項目

[ライブラリ関数](../c-language/library-functions.md)
