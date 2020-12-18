---
description: '詳細情報: double 型'
title: double 型
ms.date: 11/04/2016
helpviewer_keywords:
- mantissas, floating-point variables
- type double
- portability [C++], type double
- double data type
ms.assetid: 17c85b24-1475-4d41-a03c-ddf2d6561d34
ms.openlocfilehash: c30af4ef432251ddf38be2172102ff7a63254940
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242848"
---
# <a name="type-double"></a>double 型

double 型の倍精度浮動小数点値のサイズは 8 バイトです。 形式は、float 形式に似ています。ただし、エクセス 1023 形式の 11 ビット指数部と 52 ビット仮数部に、暗黙の上位 1 ビットを持ちます。 この形式では、およそ 1.7E-308 から 1.7E+308 の範囲を double 型で表現します。

**Microsoft 固有の仕様**

double 型は 64 ビットです。符号が 1 ビット、指数部が 11 ビット、仮数部が 52 ビットです。 その範囲は 15 桁以上の精度で、+/-1.7E308 です。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[基本型の格納](../c-language/storage-of-basic-types.md)
