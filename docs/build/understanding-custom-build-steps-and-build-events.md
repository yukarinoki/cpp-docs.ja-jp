---
title: カスタム ビルド ステップとビルド イベントについて
ms.date: 11/04/2016
helpviewer_keywords:
- builds [C++], events
- custom build steps [C++], customizing builds
- events [C++], build
- custom build steps [C++]
- build steps [C++]
- build events [C++], order of events and build steps
- build steps [C++], build events
- builds [C++], custom build steps
ms.assetid: beb2f017-3e9f-4b2c-9b57-2572fd2628e4
ms.openlocfilehash: 5bc402ad8999f1864c7e6b1155da3c68862dda97
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827741"
---
# <a name="understanding-custom-build-steps-and-build-events"></a>カスタム ビルド ステップとビルド イベントについて

Visual C++ 開発環境では、ビルド処理をカスタマイズする基本的な方法が 3 つあります。

- **カスタム ビルド ステップ**

   カスタム ビルド ステップは、プロジェクトに関連付けられたビルド規則です。 カスタム ビルド ステップでは、実行するコマンド ライン、追加の入力または出力ファイル、および表示するメッセージを指定できます。 詳細については、「[方法 :MSBuild プロジェクトへのカスタム ビルド ステップの追加](how-to-add-a-custom-build-step-to-msbuild-projects.md)します。

- **カスタム ビルド ツール**

   カスタム ビルド ツールは、1 つ以上のファイルに関連付けられているビルド規則です。 カスタム ビルド ステップは、入力ファイルをカスタム ビルド ツールに渡すことができ、その結果、1 つ以上の出力ファイルが生成されます。 たとえば、MFC アプリケーションのヘルプ ファイルは、カスタム ビルド ツールを使用してビルドされます。 詳細については、「[方法 :カスタム ビルド ツール MSBuild プロジェクトを追加する](how-to-add-custom-build-tools-to-msbuild-projects.md)と[ビルド ツールのユーザー設定を指定する](specifying-custom-build-tools.md)します。

- **ビルド イベント**

   ビルド イベントでは、プロジェクトのビルドをカスタマイズできます。 *ビルド前*、*リンク前*、*ビルド後*の 3 つのビルド イベントがあります。 ビルド イベントでは、ビルド処理の特定の時点で発生するアクションを指定できます。 たとえば、ビルド イベントを使用して、プロジェクトのビルドが終了した後でファイルを **regsvr32.exe** で登録できます。 詳細については、「[ビルド イベントの指定](specifying-build-events.md)」を参照してください。

「[ビルドのカスタマイズのトラブルシューティング](troubleshooting-build-customizations.md)」は、カスタム ビルド ステップとビルド イベントを意図したとおりに実行するために役立ちます。

カスタム ビルド ステップまたはビルド イベントの出力書式により、ツールの操作性を向上させることもできます。 詳細については、「[カスタム ビルド ステップまたはビルド イベントの出力の書式設定](formatting-the-output-of-a-custom-build-step-or-build-event.md)」を参照してください。

ビルド イベントとカスタム ビルド ステップは、他のビルド ステップと共に次の順序で実行されます。

1. ビルド前のイベント

2. 各ファイルに対するカスタム ビルド ツール

3. MIDL

4. リソース コンパイラ

5. C/C++ コンパイラ

6. Pre-Link イベント

7. リンカーまたはライブラリアン (必要に応じて)

8. マニフェスト ツール

9. BSCMake

10. プロジェクトに対するカスタム ビルド ステップ

11. ビルド後のイベント

`custom build step on the project` と `post-build event`は、他のすべてのビルド処理が完了した後に連続して実行されます。

## <a name="in-this-section"></a>このセクションの内容

[カスタム ビルド ツールを指定します。](specifying-custom-build-tools.md)<br/>
[ビルド イベントを指定します。](specifying-build-events.md)<br/>
[ビルドのカスタマイズをトラブルシューティングします。](troubleshooting-build-customizations.md)<br/>
[カスタム ビルド ステップまたはビルド イベントの出力の形式](formatting-the-output-of-a-custom-build-step-or-build-event.md)<br/>

## <a name="see-also"></a>関連項目

[Visual Studio プロジェクトの C++](creating-and-managing-visual-cpp-projects.md)<br>
[ビルドのコマンドとプロパティの共通マクロ](reference/common-macros-for-build-commands-and-properties.md)
