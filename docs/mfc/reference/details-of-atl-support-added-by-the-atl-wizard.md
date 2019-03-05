---
title: ATL ウィザードで追加した ATL サポートの詳細
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.atl.support
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
ms.openlocfilehash: 0b849ffb585ef99512cc68e1c734dc5b3a87d507
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304926"
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>ATL ウィザードで追加した ATL サポートの詳細

ときにする[既存の MFC の実行可能ファイルまたは DLL に ATL サポートを追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)、Visual C によって、既存の MFC プロジェクトに次の変更 (この例で、プロジェクトと呼ばれる`MFCEXE`)。

- 2 つの新しいファイル (.idl ファイルと、サーバーの登録に使用される .rgs ファイル) が追加されます。

- (Mfcexe.h および Mfcexe.cpp) アプリケーションのメイン ヘッダーと実装ファイル内の新しいクラス (から派生した`CAtlMFCModule`) が追加されます。 コードを追加、新しいクラスだけでなく`InitInstance`登録します。 コードにも追加、`ExitInstance`クラス オブジェクトを取り消すための関数。 ヘッダー ファイルに最後に、2 つの新しいヘッダー ファイル (Initguid.h と Mfcexe_i.c) ファイルに含まれる、実装、宣言と初期化の新しい Guid、 `CAtlMFCModule`-クラスを派生します。

- サーバーを正しく登録するには、新しい .rgs ファイルのエントリは、プロジェクトのリソース ファイルに追加されます。

## <a name="notes-for-dll-projects"></a>DLL プロジェクトのノート

MFC DLL プロジェクトに ATL サポートを追加する場合は、いくつかの違いが表示されます。 コードに追加、`DLLRegisterServer`と`DLLUnregisterServer`関数を登録すると、DLL の登録を解除します。 コードにも追加[DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow)と[DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject)します。

## <a name="see-also"></a>関連項目

[MFC プロジェクトでの ATL サポート](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)<br/>
[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[クラス各部へのジャンプ](../../ide/navigating-the-class-structure-visual-cpp.md)
