---
title: コモン ダイアログ クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a937ded9fe356627e36ad0262e749446553aa91
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379724"
---
# <a name="common-dialog-classes"></a>コモン ダイアログ クラス

クラスに加えて[CDialog](../mfc/reference/cdialog-class.md)、MFC にはいくつかのクラスから派生した`CDialog`に次の表に示すように、一般的に使用されるダイアログ ボックスをカプセル化します。 ダイアログ ボックスをカプセル化された「コモン ダイアログ ボックス」と呼ばれます、Windows コモン ダイアログ ライブラリ (COMMDLG の一部であります。DLL) です。 ダイアログ テンプレート リソースとこれらのクラスのコードは、Windows 3.1 以降のバージョンの一部であるコモン ダイアログ ボックスに、Windows で提供します。

### <a name="common-dialog-classes"></a>コモン ダイアログ クラス

|派生ダイアログ クラス|目的|
|--------------------------|-------------|
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|により、ユーザーが色を選択します。|
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|開くか保存するファイル名を選択できます。|
|[CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|ユーザーが検索の開始操作や置換テキスト ファイルで操作できます。|
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|ユーザーがフォントを指定できます。|
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|ユーザーが印刷ジョブの情報を指定できます。|
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Windows 印刷 プロパティ シートです。|

コモン ダイアログ クラスの詳細については、各クラス名を参照してください、 *MFC リファレンス*します。 MFC では、多数の OLE の標準的なダイアログ クラスも提供します。 これらのクラスについては、基本クラスを参照してください。 [COleDialog](../mfc/reference/coledialog-class.md)の、 *MFC リファレンス*します。

その他の 3 つの MFC クラスでは、ダイアログのような特性があります。 クラスについて[CFormView](../mfc/reference/cformview-class.md)、 [CRecordView](../mfc/reference/crecordview-class.md)、および[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)、内のクラスを参照してください、 *MFC リファレンス*します。 クラスについて[CDialogBar](../mfc/reference/cdialogbar-class.md)を参照してください[ダイアログ バー](../mfc/dialog-bars.md)します。

## <a name="see-also"></a>関連項目

[ダイアログ ボックス](../mfc/dialog-boxes.md)<br/>
[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[OLE のダイアログ ボックス](../mfc/dialog-boxes-in-ole.md)

