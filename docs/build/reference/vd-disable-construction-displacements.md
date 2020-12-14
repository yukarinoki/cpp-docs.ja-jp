---
description: 詳細については、「/vd (コンストラクションの変位を無効にする)」を参照してください。
title: /vd (ディスプレイスメントの無効化)
ms.date: 11/04/2016
f1_keywords:
- /vd
helpviewer_keywords:
- -vd0 compiler option [C++]
- vd1 compiler option [C++]
- /vdn (Disable Construction Displacement) compiler option
- constructor displacements
- vtordisp fields
- /vd0 compiler option [C++]
- -vd1 compiler option [C++]
- /vd1 compiler option [C++]
- displacements compiler option
- vd0 compiler option [C++]
- Disable Construction Displacements compiler option
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
ms.openlocfilehash: 9c90e2fa4f93ea0ba3892a07e13f2a15e848d608
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253196"
---
# <a name="vd-disable-construction-displacements"></a>/vd (ディスプレイスメントの無効化)

## <a name="syntax"></a>構文

```
/vdn
```

## <a name="arguments"></a>引数

**0**<br/>
Vtordisp コンストラクター/デストラクターのディスプレイスメントメンバーを非表示にします。 このオプションは、すべてのクラスコンストラクターとデストラクターが仮想関数を仮想的に呼び出すことが確実である場合にのみ選択してください。

**1**<br/>
隠し vtordisp コンストラクター/デストラクターのディスプレイスメントメンバーの作成を有効にします。 これは既定の設定です。

**2**<br/>
構築中のオブジェクトに対して [Dynamic_cast 演算子](../../cpp/dynamic-cast-operator.md) を使用できるようにします。 たとえば、仮想基底クラスから派生クラスに dynamic_cast ます。

仮想関数を持つ仮想ベースがある場合、 **/vd2** は vtordisp フィールドを追加します。 **/vd1** は十分です。 **/Vd2** が必要な最も一般的なケースは、仮想ベースの唯一の仮想関数がデストラクターである場合です。

## <a name="remarks"></a>解説

これらのオプションは、仮想ベースを使用する C++ コードにのみ適用されます。

Visual C++ は、仮想継承が使用される場合に、C++ の構築のディスプレイスメントをサポートします。 構築の変位は、仮想基底クラスで宣言され、派生クラスでオーバーライドされた仮想関数が、さらに派生したクラスの構築時にコンストラクターから呼び出された場合に作成される問題を解決します。

問題は、 **`this`** クラスの仮想基底クラスへの変位と、その派生クラスへの変位との差が原因で、仮想関数に正しくないポインターが渡される可能性があることです。 このソリューションでは、クラスの各仮想ベースに対して、vtordisp フィールドと呼ばれる1つの構築変位調整が提供されます。

既定では、vtordisp フィールドは、コードがユーザー定義のコンストラクターとデストラクターを定義し、仮想基底の仮想関数もオーバーライドするたびに導入されます。

これらのオプションは、ソースファイル全体に影響します。 [Vtordisp](../../preprocessor/vtordisp.md)を使用して、クラスごとに vtordisp フィールドを非表示にしてから再び有効にします。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション]  ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
