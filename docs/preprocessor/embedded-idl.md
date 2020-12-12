---
description: 詳細については、「embedded_idl import 属性」を参照してください。
title: embedded_idl インポート属性
ms.date: 08/29/2019
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: a56c6e664c082db4b6eac078b7133a1ead947d3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300594"
---
# <a name="embedded_idl-import-attribute"></a>embedded_idl インポート属性

**C++ 固有の仕様**

属性によって生成されたコードが保存されているファイルにタイプライブラリを書き込むかどうかを指定し `.tlh` ます。

## <a name="syntax"></a>構文

> **#import** *タイプライブラリ* **embedded_idl** [ **(** { **"emitidl"**  |  **"no_emitidl"** } **)** ]

### <a name="parameters"></a>パラメーター

**emitidl**\
*タイプライブラリ* からインポートされた型情報は、属性付きプロジェクト用に生成された IDL に存在します。 この動作は既定値であり、にパラメーターを指定しない場合は有効です `embedded_idl` 。

**"no_emitidl"**\
*タイプライブラリ* からインポートされた型情報が、属性付きプロジェクト用に生成された IDL に存在しません。

## <a name="example"></a>例

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[#import 属性](../preprocessor/hash-import-attributes-cpp.md)\
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)
