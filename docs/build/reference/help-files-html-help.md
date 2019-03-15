---
title: ヘルプ ファイル (HTML ヘルプ)
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], HTML Help files
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
ms.openlocfilehash: cde4809fa270e66081088d68d806e637f64e5344
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826277"
---
# <a name="help-files-html-help"></a>ヘルプ ファイル (HTML ヘルプ)

MFC アプリケーション ウィザードの [[高度な機能]](../../mfc/reference/advanced-features-mfc-application-wizard.md) ページで **[ポップ ヒント]** チェック ボックスをオンにしてから **[HTML Help format]\(HTML ヘルプ フォーマット\)** を選択して、アプリケーションに HTML 形式のヘルプ サポートを追加すると、以下のファイルが作成されます。

|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|
|---------------|------------------------|--------------------------------|-----------------|
|*Projname*.hhp|*Projname*\hlp|HTML ヘルプ ファイル|ヘルプ プロジェクト ファイルです。 これには、ヘルプ ファイルを .hxs ファイルまたは .chm ファイルにコンパイルするために必要なデータが含まれます。|
|*Projname*.hhk|*Projname*\hlp|HTML ヘルプ ファイル|ヘルプ トピックのインデックスが含まれています。|
|*Projname*.hhc|*Projname*\hlp|HTML ヘルプ ファイル|ヘルプ プロジェクトの内容です。|
|Makehtmlhelp.bat|*Projname*|ソース ファイル|プロジェクトのコンパイル時に、ヘルプ プロジェクトをビルドするためにシステムで使用します。|
|Afxcore.htm|*Projname*\hlp|HTML のヘルプ トピック|標準の MFC コマンドと画面オブジェクト用の標準のヘルプ トピックが含まれています。 このファイルに独自のヘルプ トピックを追加できます。|
|Afxprint.htm|*Projname*\hlp|HTML のヘルプ トピック|出力コマンドのヘルプ トピックが含まれています。|
|*.jpg; \*.gif|*Projname*\hlp\Images|リソース ファイル (Visual Studio)|生成された別のヘルプ ファイル トピックのイメージが含まれています。|

## <a name="see-also"></a>関連項目

[Visual C++ プロジェクトに対して作成されるファイルの種類](file-types-created-for-visual-cpp-projects.md)
