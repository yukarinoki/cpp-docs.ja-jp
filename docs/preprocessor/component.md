---
description: pragmaMicrosoft C/c + + での component ディレクティブの詳細について説明します。
title: 成分 pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.component
- component_CPP
helpviewer_keywords:
- component pragma
- pragma, component
no-loc:
- pragma
ms.openlocfilehash: 68a4117439390c6ec978ae9d766efb395a4ceaa4
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712948"
---
# <a name="component-no-locpragma"></a>`component` pragma

ソースファイル内の参照情報または依存関係情報の収集を制御します。

## <a name="syntax"></a>構文

> **`#pragma component( browser,`** { **`on`** \| **`off`** } \[ **`,`** **`references`** \[ **`,`** *名前* ]] **`)`** \
> **`#pragma component( minrebuild,`** { **`on`** \| **`off`** } **`)`** \
> **`#pragma component( mintypeinfo,`** { **`on`** \| **`off`** } **`)`**

## <a name="remarks"></a>解説

### <a name="browser"></a>Browser

情報収集のオン/オフを切り替えます。また特定の名前を指定して情報収集の際に無視できます。

On または off を使用すると、前方から参照情報のコレクションが制御され pragma ます。 例:

```cpp
#pragma component(browser, off)
```

上のプラグマは、コンパイラによるブラウザー情報の収集を停止します。

> [!NOTE]
> これを使用してブラウザー情報の収集を有効にするには pragma 、 [最初に参照情報を有効にする必要があり](../build/reference/building-browse-information-files-overview.md)ます。

オプションは、 **`references`** *name* 引数と共に、または指定せずに使用できます。 **`references`***名前* を指定せずにを使用すると、参照の収集がオンまたはオフになります (ただし、その他の参照情報は引き続き収集されます)。 例:

```cpp
#pragma component(browser, off, references)
```

このプラグマは、コンパイラによる参照情報の収集を停止します。

名前を指定してを使用する **`references`** と、[  **`off`** 参照情報] ウィンドウに *名前* への参照が表示されなくなります。 この構文を使用して必要のない名前と型を無視することで、ブラウザー情報ファイルのサイズを縮小できます。 例:

```cpp
#pragma component(browser, off, references, DWORD)
```

その時点以降の DWORD への参照を無視します。 次を使用して、DWORD への参照の収集をオンにすることができ **`on`** ます。

```cpp
#pragma component(browser, on, references, DWORD)
```

これは、 *名前* への参照の収集を再開する唯一の方法です。無効にした *名前* は、明示的に有効にする必要があります。

プリプロセッサによって *名前* が拡張されないようにするには (NULL を0に拡張するなど)、次のように引用符で囲みます。

```cpp
#pragma component(browser, off, references, "NULL")
```

### <a name="minimal-rebuild"></a>最小リビルド

非推奨の[ `/Gm` (簡易リビルドを有効にする)](../build/reference/gm-enable-minimal-rebuild.md)機能を使用するには、コンパイラが C++ クラスの依存関係情報を作成して格納する必要があります。これにはディスク領域が必要です。 ディスク領域を節約するために、 `#pragma component( minrebuild, off )` 依存関係情報を収集する必要がない場合 (たとえば、不変のヘッダーファイルで) を使用できます。 `#pragma component( minrebuild, on )`不変のクラスの後に挿入して、依存関係コレクションを再び有効にします。

### <a name="reduce-type-information"></a>型情報を減らす

オプションを指定すると、 **`mintypeinfo`** 指定した領域のデバッグ情報が減少します。 この情報は量が多く、.pdb ファイルと .obj ファイルに影響を与えます。 領域内のクラスおよび構造体をデバッグすることはできません **`mintypeinfo`** 。 オプションを使用すると、 **`mintypeinfo`** 次の警告が発生しないようにすることができます。

```cmd
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information
```

詳細については、「 [ `/Gm` (簡易リビルドを有効にする)](../build/reference/gm-enable-minimal-rebuild.md)コンパイラオプション」を参照してください。

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
