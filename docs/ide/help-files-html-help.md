---
title: ヘルプ ファイル (HTML ヘルプ)
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], HTML Help files
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
ms.openlocfilehash: dc98e9794200e2a317c7db2b0b513a254efff275
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480380"
---
# <a name="help-files-html-help"></a>ヘルプ ファイル (HTML ヘルプ)

MFC アプリケーション ウィザードの [[高度な機能]](../mfc/reference/advanced-features-mfc-application-wizard.md) ページで **[ポップ ヒント]** チェック ボックスをオンにしてから **[HTML Help format]\(HTML ヘルプ フォーマット\)** を選択して、アプリケーションに HTML 形式のヘルプ サポートを追加すると、以下のファイルが作成されます。

|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*.hhp|*Projname*\hlp|HTML ヘルプ ファイル|ヘルプ プロジェクト ファイルです。 これには、ヘルプ ファイルを .hxs ファイルまたは .chm ファイルにコンパイルするために必要なデータが含まれます。|
|*Projname*.hhk|*Projname*\hlp|HTML ヘルプ ファイル|ヘルプ トピックのインデックスが含まれています。|
|*Projname*.hhc|*Projname*\hlp|HTML ヘルプ ファイル|ヘルプ プロジェクトの内容です。|
|Makehtmlhelp.bat|*Projname*|ソース ファイル|プロジェクトのコンパイル時に、ヘルプ プロジェクトをビルドするためにシステムで使用します。|
|Afxcore.htm|*Projname*\hlp|HTML のヘルプ トピック|標準の MFC コマンドと画面オブジェクト用の標準のヘルプ トピックが含まれています。 このファイルに独自のヘルプ トピックを追加できます。|
|Afxprint.htm|*Projname*\hlp|HTML のヘルプ トピック|出力コマンドのヘルプ トピックが含まれています。|
|*.jpg; \*.gif|*Projname*\hlp\Images|リソース ファイル (Visual Studio)|生成された別のヘルプ ファイル トピックのイメージが含まれています。|

## <a name="see-also"></a>参照

[Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)