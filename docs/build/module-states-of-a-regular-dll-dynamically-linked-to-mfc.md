---
description: '詳細情報: MFC と動的にリンクされるレギュラー MFC DLL のモジュール状態'
title: MFC と動的にリンクされるレギュラー MFC DLL のモジュール状態
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- module states [C++]
- MFC DLLs [C++], regular MFC DLLs
- module states [C++], regular MFC DLLs dynamically linked to
- DLLs [C++], module states
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
ms.openlocfilehash: 4cf1720e7aff21f13b7486517e626307ef6731a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187508"
---
# <a name="module-states-of-a-regular-mfc-dll-dynamically-linked-to-mfc"></a>MFC と動的にリンクされるレギュラー MFC DLL のモジュール状態

通常の MFC DLL を MFC DLL に動的にリンクする機能を使用すると、非常に複雑な構成が可能になります。 たとえば、通常の MFC DLL とそれを使用する実行可能ファイルによって、MFC DLL と任意の MFC 拡張 DLL の両方に動的にリンクできます。

この構成では、現在の `CWinApp` オブジェクトへのポインターやハンドル マップなど、MFC グローバル データに関して問題が発生します。

MFC バージョン 4.0 より前のバージョンでは、このグローバル データは MFC DLL 自体に存在し、プロセス内のすべてのモジュールで共有されていました。 Win32 DLL を使用する各プロセスでは、DLL のデータの独自のコピーが取得されるため、このスキームによってプロセスごとのデータを追跡する簡単な方法が提供されました。 また、AFXDLL モデルでは、プロセス内には `CWinApp` オブジェクトが 1 つとハンドル マップのセットが 1 つしかないと想定されていたため、これらの項目は MFC DLL 自体で追跡できました。

ただし、通常の MFC DLL を MFC DLL に動的にリンクする機能により、1 つのプロセスに複数の `CWinApp` オブジェクト、および複数のハンドル マップ セットを含めることができるようになりました。 MFC では、使用すべきものをどのように追跡しているでしょうか。

このソリューションでは、各モジュール (アプリケーションまたは通常の MFC DLL) に、このグローバル状態情報の独自のコピーを提供しています。 そのため、通常の MFC DLL で **AfxGetApp** を呼び出すと、実行可能ファイル内ではなく、DLL 内の `CWinApp` オブジェクトへのポインターが返されます。 この MFC グローバル データのモジュールごとのコピーはモジュール状態と呼ばれ、[MFC テクニカル ノート 58](../mfc/tn058-mfc-module-state-implementation.md) で説明されています。

MFC 共通ウィンドウ プロシージャは自動的に正しいモジュール状態に切り替わるので、通常の MFC DLL に実装されているメッセージ ハンドラーでそれを心配する必要はありません。 ただし、実行可能ファイルから通常の MFC DLL を呼び出す場合、現在のモジュールの状態を DLL のものに明示的に設定する必要があります。 これを行うには、DLL からエクスポートされたすべての関数で **AFX_MANAGE_STATE** マクロを使用します。 これを行うには、DLL からエクスポートされた関数の先頭に次のコード行を追加します。

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [MFC モジュールの状態データの管理](../mfc/managing-the-state-data-of-mfc-modules.md)

- [MFC と動的にリンクされる標準 MFC DLL](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC 拡張 DLL](extension-dlls-overview.md)

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
