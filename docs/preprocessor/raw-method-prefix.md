---
description: '詳細については、次を参照してください: raw_method_prefix'
title: raw_method_prefix
ms.date: 08/29/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: 9e05f70814e48a4460287e96905b543f7d76dde6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201990"
---
# <a name="raw_method_prefix"></a>raw_method_prefix

**C++ 固有の仕様**

名前の衝突を避けるために異なるプレフィックスを指定します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **raw_method_prefix (** "*prefix*" **)**

### <a name="parameters"></a>パラメーター

*外線*\
使用されるプレフィックス。

## <a name="remarks"></a>解説

低レベルのプロパティとメソッドは、 **raw_** の既定のプレフィックスを使用して、という名前のメンバー関数によって公開されます。これにより、上位レベルのエラー処理メンバー関数との名前の競合を回避できます。

> [!NOTE]
> **Raw_method_prefix** 属性の効果は、 [raw_interfaces_only](raw-interfaces-only.md)属性の有無によって変更されません。 プレフィックスを指定する場合、 **raw_method_prefix** は常により優先され `raw_interfaces_only` ます。 両方の属性が同じステートメントで使用されている場合は、 `#import` **raw_method_prefix** 属性で指定したプレフィックスが使用されます。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
