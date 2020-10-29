---
title: ATL ウィザードで追加した ATL サポートの詳細
ms.date: 08/20/2019
f1_keywords:
- vc.codewiz.atl.support
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
ms.openlocfilehash: aeac01ce58deb429f14058c06524dff53abde060
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924437"
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>ATL ウィザードで追加した ATL サポートの詳細

::: moniker range=">=msvc-160"

既存の [MFC 実行可能ファイルまたは DLL に atl サポートを追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)すると、Visual Studio によって既定では、 *フレームワーク* という名前のヘッダーファイルが追加されます。このヘッダーファイルには、 `#include` `#define` プロジェクトで atl を使用できるようにするプリプロセッサディレクティブが含まれています。 以前のバージョンの Visual Studio で行ったように、追加のファイルやクラスは追加されません。

::: moniker-end

::: moniker range="<=msvc-150"

既存の [mfc 実行可能ファイルまたは DLL に ATL サポートを追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)すると、Visual Studio によって既存の mfc プロジェクトが次のように変更されます (この例では、プロジェクトが呼び出され `MFCEXE` ます)。

- 2つの新しいファイル (サーバーの登録に使用される .idl ファイルと .rgs ファイル) が追加されます。

- メインアプリケーションのヘッダーおよび実装ファイル (Mfcexe .h と Mfcexe .cpp) では、(から派生した) 新しいクラス `CAtlMFCModule` が追加されます。 新しいクラスに加えて、コードは登録のためにに追加されて `InitInstance` います。 また、クラスオブジェクトを取り消すために、関数にコードが追加され `ExitInstance` ます。 最後に、ヘッダーファイルに2つの新しいヘッダーファイル (Initguid と Mfcexe_i) が実装ファイルに含まれており、派生クラスの新しい Guid を宣言して初期化してい `CAtlMFCModule` ます。

- サーバーを適切に登録するために、新しい .rgs ファイルのエントリがプロジェクトのリソースファイルに追加されます。

::: moniker-end

## <a name="notes-for-dll-projects"></a>DLL プロジェクトのメモ

MFC DLL プロジェクトに ATL サポートを追加すると、いくつかの相違点が表示されます。 `DLLRegisterServer` `DLLUnregisterServer` DLL を登録および登録解除するためのおよび関数にコードが追加されました。 コードは [DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) と [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject)にも追加されます。

## <a name="see-also"></a>こちらもご覧ください

[MFC プロジェクトでの ATL のサポート](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)<br/>
[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[クラスの追加](../../ide/adding-a-class-visual-cpp.md)<br/>
[メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[仮想関数のオーバーライド](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[クラス各部へのジャンプ](../../ide/navigate-code-cpp.md)
