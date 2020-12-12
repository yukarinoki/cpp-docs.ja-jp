---
description: 詳細については、「high_method_prefix import 属性」を参照してください。
title: high_method_prefix インポート属性
ms.date: 08/29/2019
f1_keywords:
- high_method_prefix
helpviewer_keywords:
- high_method_prefix attribute
ms.assetid: cacebf09-12f5-4919-ad40-939e206e340c
ms.openlocfilehash: 0ebf73892ad1ea544f3deee726695bb8e209cb2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167488"
---
# <a name="high_method_prefix-import-attribute"></a>high_method_prefix インポート属性

**C++ 固有の仕様**

高レベルのプロパティおよびメソッドの名前付けで使用されるプレフィックスを指定します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **high_method_prefix (** "*prefix*" **)**

### <a name="parameters"></a>パラメーター

*外線*\
使用されるプレフィックス。

## <a name="remarks"></a>解説

既定では、高度なエラー処理のプロパティとメソッドは、プレフィックスなしの名前のメンバー関数によって公開されます。 名前はタイプ ライブラリから取り込まれます。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
