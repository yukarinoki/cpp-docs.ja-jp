---
description: 詳細については、「high_property_prefixes import 属性」を参照してください。
title: high_property_prefixes インポート属性
ms.date: 08/29/2019
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: af6835f5835c23dceadbb5152e36b0dabcbb8c98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167475"
---
# <a name="high_property_prefixes-import-attribute"></a>high_property_prefixes インポート属性

**C++ 固有の仕様**

3 つのプロパティ メソッドの代替プレフィックスを指定します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **high_property_prefixes (** "*getprefix*" **、** "*putprefix*" **、** "*putrefprefix*" **)**

### <a name="parameters"></a>パラメーター

*GetPrefix*\
メソッドに使用されるプレフィックス `propget` 。

*PutPrefix*\
メソッドに使用されるプレフィックス `propput` 。

*PutRefPrefix*\
メソッドに使用されるプレフィックス `propputref` 。

## <a name="remarks"></a>解説

既定では、高レベルのエラー処理 `propget` 、 `propput` 、および `propputref` メソッドは、 `Get` それぞれプレフィックス、、およびを持つという名前のメンバー関数によって公開され `Put` `PutRef` ます。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
