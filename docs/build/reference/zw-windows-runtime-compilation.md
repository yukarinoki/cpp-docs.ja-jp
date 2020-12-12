---
description: 詳細については、次を参照してください:/ZW (Windows ランタイムのコンパイル)
title: /ZW (Windows ランタイムのコンパイル)
ms.date: 04/08/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
ms.openlocfilehash: b2c39cdfb3f1d22d12c8d07b1e844c550a7a0e3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273918"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (Windows ランタイムのコンパイル)

Microsoft C++ コンポーネント拡張機能をサポートするためのソースコードをコンパイルして、ユニバーサル Windows プラットフォーム (UWP) アプリを作成します。

**/ZW** を使用してコンパイルする場合は、必ず **/ehsc** を指定します。

## <a name="syntax"></a>構文

```cpp
/ZW /EHsc
/ZW:nostdlib /EHsc
```

## <a name="arguments"></a>引数

**nostdlib**<br/>
Platform.winmd、Windows.Foundation.winmd、および他の既定の Windows メタデータ (.winmd) ファイルがコンパイルで自動に含まれていないことを示します。 代わりに、Windows メタデータファイルを明示的に指定するには、 [/fu (Forced #using File)](fu-name-forced-hash-using-file.md) コンパイラオプションを使用する必要があります。

## <a name="remarks"></a>解説

**/ZW** オプションを指定すると、コンパイラは次の機能をサポートします。

- アプリが Windows ランタイムで実行するために必要なメタデータファイル、名前空間、データ型、および関数。

- 自動参照-Windows ランタイムオブジェクトの数をカウントし、オブジェクトの参照カウントがゼロになるとオブジェクトを自動的に破棄します。

インクリメンタルリンカーでは、 **/ZW** オプションを使用して .obj ファイルに含まれる Windows メタデータはサポートされていないため、非推奨の [/Gm (簡易リビルドの有効化)](gm-enable-minimal-rebuild.md) オプションは **/ZW** と互換性がありません。

詳細については、「 [Visual C++ 言語リファレンス](../../cppcx/visual-c-language-reference-c-cx.md)」を参照してください。

## <a name="requirements"></a>要件

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
