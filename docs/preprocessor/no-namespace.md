---
description: 詳細については、「no_namespace import 属性」を参照してください。
title: no_namespace インポート属性
ms.date: 08/29/2019
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: e1503015f455af65a138e4e3e6843fd0516d2773
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333318"
---
# <a name="no_namespace-import-attribute"></a>no_namespace インポート属性

**C++ 固有の仕様**

コンパイラが名前空間名を生成しないことを指定します。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **no_namespace**

## <a name="remarks"></a>解説

`#import` ヘッダー ファイルのタイプ ライブラリの内容は、通常、特定の名前空間で定義されます。 名前空間の名前は、 `library` 元の IDL ファイルのステートメントで指定します。 **No_namespace** 属性が指定されている場合、この名前空間はコンパイラによって生成されません。

別の名前空間名を使用する場合は、代わりに [rename_namespace](../preprocessor/rename-namespace.md) 属性を使用します。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
