---
description: 詳細については、「リンカツール Error LNK1312」を参照してください。
title: リンカ ツール エラー LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: d861b6976f9b065e3a693e916164879a3311d3db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193631"
---
# <a name="linker-tools-error-lnk1312"></a>リンカ ツール エラー LNK1312

ファイルが無効であるか壊れています: アセンブリをインポートできません

アセンブリをビルドするときに、 **/clr** でコンパイルされたモジュールまたはアセンブリ以外のファイルが、 **/assemblymodule** リンカーオプションに渡されました。  オブジェクトファイルを **/Dns モジュール** に渡した場合は、 **/assemblymodule** ではなく、直接リンカーにオブジェクトを渡します。

## <a name="examples"></a>例

次の例では、.obj ファイルを作成しました。

```cpp
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

次の例では、LNK1312 が生成されます。

```cpp
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```
