---
title: コンパイルとマルチ スレッド プログラムのリンク |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- compiling multithreaded programs
- multithreading [C++], linking programs
- threading [C++], linking programs
- multithreading [C++], compiled programs
- threading [C++], compiled programs
- compiling source code [C++], multithread programs
- linking [C++], multithread programs
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d9dcb1d7cbda7eebcede4d25de276948d638034
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412926"
---
# <a name="compiling-and-linking-multithread-programs"></a>マルチスレッド プログラムのコンパイルとリンク

Bounce.c プログラムがで導入された[マルチ スレッドの C サンプル プログラム](sample-multithread-c-program.md)します。

プログラムはコンパイルが既定でマルチ スレッドです。

### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>開発環境内でマルチ スレッド プログラム Bounce.c のコンパイルおよびリンクするには

1. **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。

1. **プロジェクトの種類**ウィンドウで、をクリックして**Win32**します。

1. **テンプレート**ウィンドウで、をクリックして**Win32 コンソール アプリケーション**、プロジェクト名とします。

1. プロジェクトに C ソース コードを含むファイルを追加します。

1. **ビルド** メニューをクリックして、プロジェクトをビルド、**ビルド**コマンド。

### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>コマンドラインからのマルチ スレッド プログラム Bounce.c コンパイルおよびリンクするには

1. コンパイルし、プログラムをリンクします。

    ```
    CL BOUNCE.C
    ```

## <a name="see-also"></a>関連項目

[C と Win32 を使用するマルチスレッド](multithreading-with-c-and-win32.md)