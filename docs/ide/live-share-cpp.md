---
title: Visual Studio での Live Share for C++ による共同作業
description: Visual Studio で Live Share for C++ を使用して、リアルタイムで共同作業とコードの共有を行います。
ms.date: 05/24/2019
ms.openlocfilehash: 0ebdd77d0e277778b48cf69024b24841f775d968
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377287"
---
# <a name="collaborate-using-live-share-for-c"></a>Live Share for C++ を使用しての共同作業

Visual Studio 2019 と Visual Studio Code では、**Live Share** を使用して C++ プロジェクトでリアルタイムに共同作業を行うことができます。 **Live Share** を使用すると、プロジェクトやその依存関係をインストールすることなく、別のユーザーがコードを編集したりデバッグすることができます。 編集が行われると、互いの編集を見ることができます。各編集には編集を行ったユーザーの名前がタグ付けされます。

![C&#43;&#43; ライブ共有編集](../ide/media/live-share-edit-cpp.png "C++でのライブ共有編集")

## <a name="live-share-host-and-guests"></a>Live Share のホストとゲスト

Live Share セッションでは、ホストと 1 人以上のゲストが存在します。 ホストとゲストはどちらも Visual Studio または Visual Studio Code のいずれかを使用できます。 Windows 上の Visual Studio 2019 ホストは、Linux 上の Visual Studio Code のゲストと共有できます。

ホストからは生産性を向上するために必要なものすべてのものがゲストに提供されます。 ゲストは、ソース コード、コンパイラ、外部の依存関係を持つ必要はなく、同じコンポーネントをインストールする必要もありません。

ホストとゲストは、次の IntelliSense 機能を使用できます。

- メンバー一覧
- パラメーターのヘルプ
- クイック ヒント
- デバッグ/ブレークポイント
- すべての参照を検索
- 定義へ移動
- シンボル検索 (Ctrl + T)
- 参照の強調表示
- 診断/エラー/波線

![C&#43;&#43; ライブ共有デバッグ](../ide/media/live-share-debug-cpp.png "C++ でのライブ共有デバッグ")

## <a name="start-and-end-a-live-share-session"></a>Live Share セッションの開始と終了

Visual Studio でライブ共有セッションを開始するには、右上の [共有] ボタンをクリックするか、または [**ファイル** > **開始コラボレーション セッション**] に移動します。 これによりコラボレーターと共有できるリンクが生成されます。

![C&#43;&#43; ライブ共有ボタン](../ide/media/live-share-button-cpp.png "ライブシェアボタン")

セッションを終了するには、**[共有]** ドロップダウンから **[End Collaboration Session]\(コラボレーション セッションの終了\)** を選択します。

![C&#43;&#43; ライブ共有ボタン](../ide/media/live-share-end-session-cpp.png "ライブシェアボタン")

## <a name="for-more-information"></a>詳細情報

Visual Studio での **Live Share** の詳細については、「[Visual Studio Live Share とは](/visualstudio/liveshare/)」を参照してください。 Visual Studio Code での Live Share の詳細については、「[Live Share](https://marketplace.visualstudio.com/items?itemName=ms-vsliveshare.vsliveshare)」を参照してください。

## <a name="see-also"></a>参照

[コードの作成とリファクタリング (C++)](writing-and-refactoring-code-cpp.md)</br>
[Visual Studio で C++コード ベース内を移動する](navigate-code-cpp.md)</br>
[C++ コードの読み取りと理解](read-and-understand-code-cpp.md)</br>
