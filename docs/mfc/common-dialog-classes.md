---
description: '詳細情報: コモンダイアログクラス'
title: コモン ダイアログ クラス
ms.date: 11/04/2016
helpviewer_keywords:
- dialog classes [MFC]
- dialog boxes [MFC], Windows common dialogs
- common dialog boxes [MFC], common dialog classes
- common dialog classes [MFC]
- MFC dialog boxes [MFC], Windows common dialogs
- Windows common dialogs [MFC]
- dialog classes [MFC], common
- common dialog boxes [MFC]
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
ms.openlocfilehash: 8ab72407c9d709ef660976105d65901398ae5b5b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310683"
---
# <a name="common-dialog-classes"></a>コモン ダイアログ クラス

MFC には、クラス [CDialog](reference/cdialog-class.md)に加えて、次の `CDialog` 表に示すように、一般的に使用されるダイアログボックスをカプセル化するから派生した複数のクラスが用意されています。 カプセル化されたダイアログボックスは、"コモンダイアログボックス" と呼ばれ、Windows コモンダイアログライブラリ (COMMDLG.DLL) の一部です。 これらのクラスのダイアログテンプレートリソースとコードは、Windows バージョン3.1 以降の一部である Windows コモンダイアログボックスに用意されています。

### <a name="common-dialog-classes"></a>コモン ダイアログ クラス

|派生ダイアログクラス|目的|
|--------------------------|-------------|
|[CColorDialog](reference/ccolordialog-class.md)|ユーザーが色を選択できるようにします。|
|[CFileDialog](reference/cfiledialog-class.md)|開くファイルまたは保存するファイル名をユーザーが選択できるようにします。|
|[CFindReplaceDialog](reference/cfindreplacedialog-class.md)|ユーザーがテキストファイルで検索または置換操作を開始できるようにします。|
|[CFontDialog](reference/cfontdialog-class.md)|ユーザーがフォントを指定できるようにします。|
|[CPrintDialog](reference/cprintdialog-class.md)|印刷ジョブの情報をユーザーが指定できるようにします。|
|[CPrintDialogEx](reference/cprintdialogex-class.md)|Windows Print プロパティシート。|

コモンダイアログクラスの詳細については、 *MFC リファレンス* の個々のクラス名を参照してください。 MFC には、OLE に使用される標準ダイアログクラスも多数用意されています。 これらのクラスの詳細については、 *MFC リファレンス* の基本クラスである [COleDialog](reference/coledialog-class.md)を参照してください。

MFC の他の3つのクラスには、ダイアログのような特性があります。 クラス [CFormView](reference/cformview-class.md)、 [CRecordView](reference/crecordview-class.md)、および [CDaoRecordView](reference/cdaorecordview-class.md)の詳細については、 *MFC リファレンス* のクラスを参照してください。 クラス [CDialogBar](reference/cdialogbar-class.md)の詳細については、「 [ダイアログバー](dialog-bars.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ダイアログボックス](dialog-boxes.md)<br/>
[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)<br/>
[ダイアログボックス (OLE の)](dialog-boxes-in-ole.md)
