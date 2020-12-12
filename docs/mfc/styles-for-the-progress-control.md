---
description: '詳細情報: プログレスコントロールのスタイル'
title: プログレス コントロールのスタイル
ms.date: 11/19/2018
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
ms.openlocfilehash: cd6ce1093f8bd2e3271a386e894d1e8dcd1a4fd7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216497"
---
# <a name="styles-for-the-progress-control"></a>プログレス コントロールのスタイル

プログレスコントロール ([CProgressCtrl:: create](../mfc/reference/cprogressctrl-class.md#create)) を最初に作成するときは、 *dwStyle* パラメーターを使用して、プログレスコントロールに必要なウィンドウスタイルを指定します。 次の一覧に、適用可能なウィンドウスタイルの詳細を示します。 コントロールは、ここに記載されているもの以外のウィンドウスタイルを無視します。 コントロールは常に子ウィンドウとして作成する必要があります (通常はダイアログボックスの親)。

|ウィンドウスタイル|効果|
|------------------|------------|
|WS_BORDER|ウィンドウの周りに境界線を作成します。|
|WS_CHILD|子ウィンドウを作成します (には常にを使用する必要があり `CProgressCtrl` ます)。|
|WS_CLIPCHILDREN|親ウィンドウ内で描画するときに、子ウィンドウによって占有される領域を除外します。 親ウィンドウを作成するときに使用します。|
|WS_CLIPSIBLINGS|子ウィンドウを互いに相対的にクリップします。|
|WS_DISABLED|最初は無効になっているウィンドウを作成します。|
|WS_VISIBLE|最初に表示されるウィンドウを作成します。|
|WS_TABSTOP|ユーザーが TAB キーを押して移動するときに、コントロールがフォーカスを受け取ることができるように指定します。|

さらに、プログレスコントロール、PBS_VERTICAL および PBS_SMOOTH にのみ適用される2つのスタイルを指定できます。

コントロールを水平方向ではなく垂直方向に回転させるには、PBS_VERTICAL を使用します。 PBS_SMOOTH を使用すると、コントロールを段階的に塗りつぶす小さい四角形を表示するのではなく、コントロールを完全に塗りつぶすことができます。

PBS_SMOOTH スタイルなし:

![標準の進行状況バーのスタイル](../mfc/media/vc4ruw1.gif "標準の進行状況バーのスタイル")

PBS_SMOOTH と PBS_VERTICAL スタイルを使用する場合:

![進行状況バーのスタイル、スムーズおよび垂直](../mfc/media/vc4ruw2.gif "進行状況バーのスタイル、スムーズおよび垂直")

詳細については、「 *MFC リファレンス*」の「[ウィンドウのスタイル](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc)」を参照してください。

## <a name="see-also"></a>関連項目

[CProgressCtrl の使い方](../mfc/using-cprogressctrl.md)
