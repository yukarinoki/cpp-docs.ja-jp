---
description: '詳細情報: ダイアログバー'
title: ダイアログ バー
ms.date: 11/19/2018
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
ms.openlocfilehash: 701954dc9ec682bd95258b26d7af1290ea2da521
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261633"
---
# <a name="dialog-bars"></a>ダイアログ バー

ダイアログバーとは、任意の種類のコントロールを含むことができる [コントロールバー](control-bars.md) の一種です。 [CDialogBar](reference/cdialogbar-class.md)オブジェクトには、モードレスダイアログボックスの特性があるため、より強力なツールバーが用意されています。

ツールバーとオブジェクトの間には、いくつかの重要な違いがあり `CDialogBar` ます。 `CDialogBar`オブジェクトはダイアログテンプレートリソースから作成されます。このリソースは、Visual C++ ダイアログエディターを使用して作成でき、任意の種類の Windows コントロールを含むことができます。 ユーザーは、tab キーを使用してコントロールを制御できます。 また、配置スタイルを指定して、ダイアログバーを親フレームウィンドウの任意の部分に揃えたり、親のサイズを変更した場合にそのままにすることもできます。 次の図は、さまざまなコントロールを含むダイアログバーを示しています。

![VC ダイアログ バー](../mfc/media/vc378t1.gif "VC ダイアログ バー") <br/>
ダイアログバー

また、オブジェクトの操作は、 `CDialogBar` モードレスダイアログボックスの操作と似ています。 ダイアログエディターを使用して、ダイアログリソースをデザインおよび作成します。

ダイアログバーの多くの1つは、ボタン以外のコントロールを含めることができることです。

から独自のダイアログクラスを派生させることは通常 `CDialog` ありませんが、通常はダイアログバーの独自のクラスを派生させません。 ダイアログバーはメインウィンドウの拡張機能であり、 **BN_CLICKED** や **EN_CHANGE** などのダイアログバーコントロール通知メッセージは、ダイアログバーのメインウィンドウの親に送信されます。

## <a name="see-also"></a>関連項目

[ユーザーインターフェイス要素](user-interface-elements-mfc.md)<br/>
[サンプル](../overview/visual-cpp-samples.md)
