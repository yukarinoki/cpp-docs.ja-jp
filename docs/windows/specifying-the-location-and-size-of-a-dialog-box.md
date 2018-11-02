---
title: ダイアログ ボックス (C++) のサイズと場所を指定します。
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [C++], size
- dialog boxes [C++], positioning
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
ms.openlocfilehash: 2c39cf5076ea38635268120da96fec6c82e23c47
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50524934"
---
# <a name="specifying-the-location-and-size-of-a-dialog-box-c"></a>ダイアログ ボックス (C++) のサイズと場所を指定します。

場所と C++ のダイアログ ボックスでは、だけでなく、場所のサイズと、内のコントロールのサイズは、ダイアログ単位で測定されます。 個々 のコントロールと、ダイアログ ボックスの値は、Visual Studio のステータス バーの選択した場合の右下に表示されます。

設定できる 3 つのプロパティがある、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window) ダイアログ ボックスを画面に表示を指定します。 **Center** 、値を設定する場合、プロパティはブール値。 **True**、画面の中央で、ダイアログ ボックスが表示されます。 設定した場合**False**、設定することができます、 **XPos**と**YPos**プロパティ ダイアログ ボックスが表示され、画面上の場所を明示的に定義します。 位置プロパティとして定義されている表示領域の左上隅からのオフセット値を`{X=0, Y=0}`します。 位置もに基づいて、 **Absolute Align**プロパティ: 場合**True**、座標は画面場合**False**座標は、ダイアログ ボックス所有者のウィンドウです。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[コントロール](../mfc/controls-mfc.md)