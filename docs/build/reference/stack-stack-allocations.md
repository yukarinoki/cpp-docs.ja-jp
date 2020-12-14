---
description: 詳細情報:/STACK (スタック割り当て)
title: /STACK (スタック割り当て)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.StackReserveSize
- VC.Project.VCLinkerTool.StackCommitSize
- /stack
helpviewer_keywords:
- STACK linker option
- -STACK linker option
- memory allocation, stack
- /STACK linker option
- stack, setting size
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
ms.openlocfilehash: 6e74b508d8cdb2340c73360bf35272d9113a0f75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224467"
---
# <a name="stack-stack-allocations"></a>/STACK (スタック割り当て)

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>解説

/STACK オプションは、スタックのサイズをバイト単位で指定します。 このオプションは、.exe ファイルのビルドだけに使用します。

`reserve` 値は、仮想メモリ内のスタック割り当ての合計サイズを指定します。 ARM、x86、および x64 コンピューターの場合、既定のスタックサイズは 1 MB です。

`commit` は、オペレーティング システムによって解釈が異なります。 Windows WindowsRT では、一度に確保する物理メモリ量です。 仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。 `commit` の値を大きく設定すると、アプリケーションに必要なスタック領域が増えたときに処理時間を節約できます。ただし、必要なメモリ量と起動時間が増えます。 ARM、x86、および x64 コンピューターの場合、既定のコミット値は 4 KB です。

引数 `reserve` と引数 `commit` の値は、10 進表記か C 言語表記で指定します。

スタックのサイズを設定するもう1つの方法は、モジュール定義 (.def) ファイルの [STACKSIZE](stacksize.md) ステートメントを使用する方法です。 両方が指定されている場合、 **STACKSIZE** はスタック割り当て (/STACK) オプションをオーバーライドします。 [EDITBIN](editbin-reference.md)ツールを使用して、.exe ファイルをビルドした後にスタックサイズを変更できます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **リンカー** ] フォルダーを選択します。

1. [ **システム** ] プロパティページを選択します。

1. 次のいずれかのプロパティを変更します。

   - **[スタックのコミット サイズ]**

   - **[スタックのサイズの設定]**

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A> プロパティを参照してください。

## <a name="see-also"></a>関連項目

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
