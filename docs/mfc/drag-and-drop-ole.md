---
title: ドラッグ アンド ドロップ (OLE)
ms.date: 11/04/2016
helpviewer_keywords:
- OLE server applications [MFC], drag and drop
- drag and drop [MFC]
- OLE applications [MFC], drag and drop
- File Manager drag and drop support [MFC]
- drag and drop [MFC], about OLE drag and drop
- OLE drag and drop [MFC]
ms.assetid: a4595350-ca06-4400-88a1-f0175c76b77b
ms.openlocfilehash: 98bd58745e56a62bf5700e9b5fe4963a7b584953
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58766808"
---
# <a name="drag-and-drop-ole"></a>ドラッグ アンド ドロップ (OLE)

OLE のドラッグ アンド ドロップ機能は、主にコピーし、データの貼り付けのショートカットです。 クリップボードにコピーまたは貼り付けを使用する場合は、いくつかの手順が必要です。 データを選択する をクリックして**切り取り**または**コピー**から、**編集** メニューの 変換先のファイル、ウィンドウまたはアプリケーションへの移行では、カーソルを置き、目的の場所をクリックします**貼り付け**から、**編集**メニュー。

OLE ドラッグ アンド ドロップは、ファイル名のみを処理し、アプリケーションにファイル名を渡す特別に設計されているファイル マネージャーのドラッグ アンド ドロップ メカニズムと異なります。 OLE ドラッグ アンド ドロップより一般的なのです。 ドラッグ アンド ドロップのデータがクリップボードに配置もできます。

OLE ドラッグ アンド ドロップを使用する場合は、プロセスから 2 つの手順を削除します。 目的の転送先 (「ドロップ ターゲット上の」) にドラッグ、マウス ボタンを離すドロップ ソース ウィンドウ (「ドロップ ソース」) からデータを選択します。 操作を使用して、メニューの必要はなくなり、コピー/貼り付けシーケンスよりも高速です。 唯一の要件は、ドロップ ソースとドロップ先の両方でなければならないことを開き、画面に少なくとも部分的に表示します。

OLE ドラッグ アンド ドロップを使用して、データ転送できます 1 つの場所から別のドキュメント間で、またはアプリケーション間で、ドキュメント内の別に。 コンテナーまたはサーバー アプリケーションでは、いずれかで実装することし、任意のアプリケーションは、ドロップ ソース、ドロップ先、またはその両方を指定できます。 アプリケーションに実装されているドロップ ソースとドロップ先の両方のサポートがある場合は、子ウィンドウ間または 1 つのウィンドウ内でドラッグ アンド ドロップが有効にします。 この機能は、アプリケーションがより簡単を使用します。

OLE のドラッグ アンド ドロップ機能を使用する場合は、「[ドラッグ アンド ドロップします。カスタマイズ](../mfc/drag-and-drop-customizing.md)します。 その記事で説明した手法を使用すると、によって、非 OLE アプリケーションのソースを削除します。 この記事[ドラッグ アンド ドロップします。ドロップ ターゲットの実装](../mfc/drag-and-drop-implementing-a-drop-target.md)OLE と非 OLE アプリケーションの両方のドロップ ターゲットのサポートを実装する方法について説明します。 MFC OLE サンプルを確認する便利なことも[OCLIENT](../overview/visual-cpp-samples.md)と[HIERSVR](../overview/visual-cpp-samples.md)します。

まだ読んでいない場合、[データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)ファミリの記事は、可能性があるようになりました。 これらの記事では、データ転送、およびアプリケーションで実装する方法の基礎について説明します。

ドラッグ アンド ドロップする方法の詳細については、次を参照してください。

- [ドラッグ アンド ドロップします。ドロップ ソースの実装](../mfc/drag-and-drop-implementing-a-drop-source.md)

- [ドラッグ アンド ドロップします。ドロップ ターゲットの実装](../mfc/drag-and-drop-implementing-a-drop-target.md)

- [ドラッグ アンド ドロップします。カスタマイズ](../mfc/drag-and-drop-customizing.md)

## <a name="see-also"></a>関連項目

[OLE](../mfc/ole-in-mfc.md)<br/>
[データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)
