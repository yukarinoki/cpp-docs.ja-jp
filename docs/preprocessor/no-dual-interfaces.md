---
description: 詳細については、「no_dual_interfaces import 属性」を参照してください。
title: no_dual_interfaces インポート属性
ms.date: 08/29/2019
f1_keywords:
- no_dual_interfaces
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
ms.openlocfilehash: 1c3010b252ac71e38312fa193520938fbb4d681a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333336"
---
# <a name="no_dual_interfaces-import-attribute"></a>no_dual_interfaces インポート属性

**C++ 固有の仕様**

コンパイラがデュアル インターフェイス メソッドのラッパー関数を生成する方法を変更します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **no_dual_interfaces**

## <a name="remarks"></a>解説

通常、ラッパーは、インターフェイスの仮想関数テーブルを通じてメソッドを呼び出します。 **No_dual_interfaces** では、ラッパーはを呼び出して、 `IDispatch::Invoke` メソッドを呼び出します。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
