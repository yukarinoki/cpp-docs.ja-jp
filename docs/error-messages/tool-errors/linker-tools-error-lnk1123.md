---
title: リンカ ツール エラー LNK1123 |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1123
dev_langs:
- C++
helpviewer_keywords:
- LNK1123
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b12a65e61c5677943b4ea1b4b85c12cfc796af45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1123"></a>リンカ ツール エラー LNK1123

> COFF への変換中に障害が発生しました : ファイルが無効であるか、または壊れています。

入力ファイルは、COFF (Common Object File Format) 形式である必要があります。 入力ファイルが COFF でない場合、リンカーによって 32 ビット OMF オブジェクトが COFF に自動変換されるか、リソース ファイルを変換するための CVTRES.EXE が実行されます。 このメッセージは、リンカーがファイルを変換できなかったことを示します。 これは、Visual Studio、Windows Development Kit、または .NET Framework の別のインストールから CVTRES.EXE の非互換バージョンを使用している場合にも発生します。

> [!NOTE]
> 旧バージョンの Visual Studio を実行している場合は、自動変換がサポートされない場合があります。

## <a name="to-fix-the-problem"></a>この問題を解決するには、次のいずれかを行います。

- Visual Studio の該当するバージョン用のすべての更新プログラムとサービス パックを適用します。 これは、Visual Studio 2010年には特に重要です。

- インクリメンタル リンクを無効にしてビルドしてみます。 メニュー バーで、**[プロジェクト]**、**[プロパティ]** の順に選びます。 **プロパティ ページ** ダイアログ ボックスで、展開**構成プロパティ**、**リンカー**です。 値を変更**インクリメンタル リンクを有効にする**に**いいえ**です。

- PATH 環境変数で最初に見つかる CVTRES.EXE のバージョンが、プロジェクトで使用されるビルド ツールのバージョン (プラットフォーム ツールセットのバージョン) と一致することを確認します。

- [埋め込みマニフェスト] のオプションをオフにしてください。 メニュー バーで、**[プロジェクト]**、**[プロパティ]** の順に選びます。 **プロパティ ページ** ダイアログ ボックスで、展開**構成プロパティ**、**マニフェスト ツール**、**の入力し、出力**です。 値を変更**埋め込みマニフェスト**に**いいえ**です。

- ファイルの種類が有効であることを確認します。 たとえば OMF オブジェクトが 16 ビットではなく 32 ビットであることを確認します。 詳細については、次を参照してください。[です。リンカー入力としての Obj ファイル](../../build/reference/dot-obj-files-as-linker-input.md)と[PE 形式](https://msdn.microsoft.com/library/windows/desktop/ms680547)です。

- ファイルが破損していないことを確認してください。 必要に応じて再構築します。

## <a name="see-also"></a>関連項目

[.obj ファイル (リンカー入力)](../../build/reference/dot-obj-files-as-linker-input.md)  
[EDITBIN リファレンス](../../build/reference/editbin-reference.md)  
[DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)  
