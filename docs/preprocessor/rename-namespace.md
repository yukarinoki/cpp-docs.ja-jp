---
description: 詳細については、「rename_namespace import 属性」を参照してください。
title: rename_namespace インポート属性
ms.date: 08/29/2019
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: 402d9c9cd8dee5979dd71e16fec1a606d8b4b996
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167384"
---
# <a name="rename_namespace-import-attribute"></a>rename_namespace インポート属性

**C++ 固有の仕様**

タイプ ライブラリの内容を含む名前空間の名前を変更します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **rename_namespace (** "*NewName*" **)**

### <a name="parameters"></a>パラメーター

*NewName*\
名前空間の新しい名前。

## <a name="remarks"></a>解説

**Rename_namespace** 属性は、名前空間の新しい名前を指定する *NewName* という1つの引数を受け取ります。

名前空間を削除するには、代わりに [no_namespace](../preprocessor/no-namespace.md) 属性を使用します。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
