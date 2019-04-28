---
title: Tasks.vs.json スキーマ リファレンス (C++)
ms.date: 02/11/2019
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: d0f62f6cddf3701da391880532bd2f554cc19130
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315054"
---
# <a name="tasksvsjson-c"></a>Tasks.vs.json (C++)

`tasks.vs.json` ファイルを "フォルダーを開く" プロジェクトに追加して任意のタスクを定義し、**ソリューション エクスプローラー**のコンテキスト メニューからそのタスクを呼び出すことができます。 すべてのビルド コマンドは `CMakeLists.txt` で指定されるため、CMake プロジェクトは通常このファイルを使用しません。 CMake 以外のビルド システムでは、ここでビルド コマンドを指定して、ビルド スクリプトを呼び出すことができます。 tasks.vs.json の使用の一般情報については、「[Customize build and debug tasks for "Open Folder" development](/visualstudio/ide/customize-build-and-debug-tasks-in-visual-studio)」("フォルダーを開く" の開発のためにビルド タスクとデバッグ タスクをカスタマイズする) を参照してください。

