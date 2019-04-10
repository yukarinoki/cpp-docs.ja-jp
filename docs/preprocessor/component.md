---
title: コンポーネント
ms.date: 04/08/2019
f1_keywords:
- vc-pragma.component
- component_CPP
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
ms.openlocfilehash: 4870860650a39d27639ad18100ba37ba14aa15c0
ms.sourcegitcommit: 39debf8c525c3951af6913ee5e514617658f8859
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424067"
---
# <a name="component"></a>コンポーネント

ブラウザー情報またはからソース ファイル内の依存関係情報のコレクションを制御します。

## <a name="syntax"></a>構文

> **#pragma component( browser,** { **on** | **off** }[**,** **references** [**,** *name* ]] **)** \
> **#pragma component( minrebuild, on** | **off )** \
> **#pragma component( mintypeinfo, on** | **off )**

## <a name="remarks"></a>Remarks

### <a name="browser"></a>ブラウザー

情報収集のオン/オフを切り替えます。また特定の名前を指定して情報収集の際に無視できます。

on または off を使用して、このプラグマ以降のブラウザー情報の収集を制御します。 例:

```cpp
#pragma component(browser, off)
```

上のプラグマは、コンパイラによるブラウザー情報の収集を停止します。

> [!NOTE]
> このプラグマを使用してブラウザー情報の収集を有効にする[ブラウズ情報を有効にする必要がありますまず](../build/reference/building-browse-information-files-overview.md)します。

`references`またはなしでオプションを使用できる、*名前*引数。 使用して`references`せず*名前*を有効または無効の収集の (ただし、収集するその他の参照情報が続行されます)。 例えば:

```cpp
#pragma component(browser, off, references)
```

このプラグマは、コンパイラによる参照情報の収集を停止します。

使用して`references`で*名前*と`off`への参照を防止*名前*がブラウザー情報ウィンドウに表示されないようにします。 この構文を使用して必要のない名前と型を無視することで、ブラウザー情報ファイルのサイズを縮小できます。 例:

```cpp
#pragma component(browser, off, references, DWORD)
```

その時点から DWORD への参照は無視されます。 使用してに戻り、DWORD への参照の収集を有効にする`on`:

```cpp
#pragma component(browser, on, references, DWORD)
```

参照情報の収集を再開する唯一の方法は、この*名前*; いずれかで明示的に有効にする必要があります*名前*をオフにします。

プリプロセッサが拡大するを防ぐために*名前*(などを 0 に NULL を拡大します)、引用符で囲みます。

```cpp
#pragma component(browser, off, references, "NULL")
```

### <a name="minimal-rebuild"></a>最小リビルド

非推奨とされる[/Gm (簡易リビルドの有効)](../build/reference/gm-enable-minimal-rebuild.md)機能には、コンパイラを作成および保存が必要です。C++クラスの依存関係については、ディスク容量。 使用することができます、ディスク領域を節約する`#pragma component( minrebuild, off )`たびに不変のヘッダー ファイルで、たとえば、依存関係情報を収集する必要はありません。 挿入`#pragma component(minrebuild, on)`後、上の変更のない依存関係のコレクションを有効にするクラスをバックアップします。

### <a name="reduce-type-information"></a>型情報の削減

`mintypeinfo`オプションが指定された領域のデバッグ情報を削減します。 この情報は量が多く、.pdb ファイルと .obj ファイルに影響を与えます。 mintypeinfo 領域では、クラスと構造をデバッグできません。 mintypeinfo オプションを使用すると、次の警告を回避するのに役立ちます。

```cmd
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information
```

詳細については、次を参照してください。、 [/Gm (簡易リビルドの有効)](../build/reference/gm-enable-minimal-rebuild.md)コンパイラ オプション。

## <a name="see-also"></a>関連項目

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)