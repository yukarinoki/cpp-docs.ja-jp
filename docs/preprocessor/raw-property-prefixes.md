---
description: 詳細については、「raw_property_prefixes import 属性」を参照してください。
title: raw_property_prefixes インポート属性
ms.date: 08/29/2019
f1_keywords:
- raw_property_prefixes
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
ms.openlocfilehash: 7289f9aeba249249ecf78ffb3ad3b32669ac9fe3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142715"
---
# <a name="raw_property_prefixes-import-attribute"></a>raw_property_prefixes インポート属性

**C++ 固有の仕様**

3 つのプロパティ メソッドの代替プレフィックスを指定します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **raw_property_prefixes (** "*getprefix*" **、** "*putprefix*" **、** "*putrefprefix*" **)**

### <a name="parameters"></a>パラメーター

*GetPrefix*\
メソッドに使用するプレフィックス `propget` 。

*PutPrefix*\
メソッドに使用するプレフィックス `propput` 。

*PutRefPrefix*\
メソッドに使用するプレフィックス `propputref` 。

## <a name="remarks"></a>解説

既定では、低レベルの `propget` 、 `propput` 、および `propputref` の各メソッドは `get_` 、それぞれ、、およびのプレフィックスを使用して名前が付けられたメンバー関数によって公開され `put_` `putref_` ます。 これらのプレフィックスは、MIDL によって生成されるヘッダー ファイルで使用される名前と互換性があります。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
