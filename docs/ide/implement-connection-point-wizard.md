---
title: 接続ポイントの実装ウィザード | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.impl.cp.overview
dev_langs:
- C++
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
ms.assetid: c117f6c6-30f0-4adb-82b4-b1f34e0f0fa8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92312bc130ed24f2aafe2e4b95e2c4bcf6381215
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429670"
---
# <a name="implement-connection-point-wizard"></a>接続ポイントの実装ウィザード

このウィザードでは、COM オブジェクトの接続ポイントを実装できます。 接続可能なオブジェクト (ソース) は、独自のインターフェイスまたは任意の発信インターフェイスの接続ポイントを公開します。 Visual C++ と Windows のいずれにも、発信インターフェイスがあるタイプ ライブラリがあります。 各発信インターフェイスは、オブジェクト上のクライアント (シンク) によって実装できます。

詳細については、「[ATL コネクション ポイント](../atl/atl-connection-points.md)」を参照してください。

- **Available type libraries\(使用可能なタイプ ライブラリ\)**

   接続ポイントを実装できるインターフェイスの定義を含む使用可能なタイプ ライブラリを表示します。 省略記号ボタンをクリックすると、使用するタイプ ライブラリを含むファイルを見つけることができます。

- **場所**

   **[Available type libraries]\(使用可能なタイプ ライブラリ\)** リストで現在選択されているタイプ ライブラリの場所を表示します。

- **インターフェイス**

   **[Available type libraries]\(使用可能なタイプ ライブラリ\)** ボックスで現在選択されているタイプ ライブラリに定義が含まれているインターフェイスを表示します。

   |転送ボタン|説明|
   |---------------------|-----------------|
   |**>**|**[Implement connection points]\(接続ポイントを実装する\)** リストに、現在 **[インターフェイス]** リストで選択されているインターフェイス名を追加します。|
   |**>>**|**[Implement connection points]\(接続ポイントを実装する\)** リストに、**[インターフェイス]** リストで使用可能なすべてのインターフェイス名を追加します。|
   |**\<**|現在 **[Implement connection points]\(接続ポイントを実装する\)** リストで選択されているインターフェイス名を削除します。|
   |**\<\<**|現在 **[Implement connection points]\(接続ポイントを実装する\)** リストに表示されているすべてのインターフェイス名を削除します。|

- **Implement connection points\(接続ポイントを実装する\)**

   **[完了]** をクリックしたときに接続ポイントを実装する、インターフェイス名を表示します。

## <a name="see-also"></a>参照

[接続ポイントの実装](../ide/implementing-a-connection-point-visual-cpp.md)