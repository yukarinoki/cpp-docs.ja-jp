---
title: /HEAP (ヒープ サイズの設定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.HeapCommitSize
- VC.Project.VCLinkerTool.HeapReserveSize
helpviewer_keywords:
- -HEAP linker option
- heap allocation, setting heap size
- /HEAP linker option
- HEAP linker option
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
ms.openlocfilehash: f155ad56ec1a90479b402e38e7ec7f3e3d80e470
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439524"
---
# <a name="heap-set-heap-size"></a>/HEAP (ヒープ サイズの設定)

```
/HEAP:reserve[,commit]
```

## <a name="remarks"></a>コメント

/Heap オプションは、ヒープのサイズをバイト単位で設定します。 このオプションは、.exe ファイルをビルドする場合にのみ使用します。

*Reserve*引数は、仮想メモリ内のヒープの合計割り当てを指定します。 既定のヒープサイズは 1 MB です。 リンカーは、指定された値を最も近い4バイトに切り上げます。

省略可能な `commit` 引数は、一度に割り当てる物理メモリの量を指定します。 仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。 `commit` 値を大きくすると、アプリケーションが必要とするヒープ領域が増えるにつれて時間が節約されますが、メモリ要件が増加し、場合によっては起動時間が長くなります。

*予約*値と `commit` 値を10進数または C 言語表記で指定します。

この機能は、 [HEAPSIZE](heapsize.md)を使用したモジュール定義ファイルを介して使用することもできます。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関する記事を参照してください。

1. **[リンカー]** フォルダーをクリックします。

1. **[システム]** プロパティページをクリックします。

1. **ヒープコミットサイズ**プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A>」と「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>」を参照してください。

## <a name="see-also"></a>参照

[MSVC リンカーのリファレンス](linking.md)<br/>
[MSVC リンカー オプション](linker-options.md)
