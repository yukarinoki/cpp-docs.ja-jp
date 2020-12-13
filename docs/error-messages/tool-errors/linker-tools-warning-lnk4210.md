---
description: 詳細については、「リンカーツールの警告 LNK4210」を参照してください。
title: リンカー ツールの警告 LNK4210
ms.date: 11/04/2016
f1_keywords:
- LNK4210
helpviewer_keywords:
- LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
ms.openlocfilehash: 7634952df026dc664aed2a2f9625a7380b3a38b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150606"
---
# <a name="linker-tools-warning-lnk4210"></a>リンカー ツールの警告 LNK4210

> セクション *セクション* は存在します。未処理の静的初期化子またはターミネータがある可能性があります

## <a name="remarks"></a>解説

一部のコードでは静的初期化子またはターミネータが導入されていますが、VCRuntime ライブラリスタートアップコードまたはそれと同等のもの (静的初期化子またはターミネータを実行する必要があります) は、アプリケーションの起動時には実行されません。 静的初期化子またはターミネータを必要とするコードの例を次に示します。

- コンストラクター、デストラクター、または仮想関数テーブルを持つグローバルクラス変数。

- コンパイル時以外の定数で初期化されたグローバル変数。

この問題を解決するには、次のいずれかを試してください。

- 静的初期化子を使用してすべてのコードを削除します。

- [/NOENTRY](../../build/reference/noentry-no-entry-point.md)は使用しないでください。 /NOENTRY を削除した後、リンカーコマンドラインから [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) を削除することが必要になる場合もあります。

- ビルドで/MT が使用されている場合は、リンカーコマンドラインに libcmt.lib、libvcruntime .lib、および libucrt を追加します。 ビルドで/MTd が使用されている場合は、libcmtd、vcruntimed .lib、および libucrtd を追加します。

- /Clr: pure コンパイルから/clr に移動する場合は、 [/entry](../../build/reference/entry-entry-point-symbol.md) オプションをリンカー行から削除します。 これにより、CRT の初期化が可能になり、アプリケーションの起動時に静的初期化子を実行できるようになります。 **/Clr: pure** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

[/Gs](../../build/reference/gs-buffer-security-check.md)コンパイラオプションでは、関数による初期化が必要です `__security_init_cookie` 。 この初期化は、で実行される VCRuntime ライブラリスタートアップコードに既定で用意されてい `_DllMainCRTStartup` ます。

- /ENTRY を使用してプロジェクトがビルドされ、/ENTRY に以外の関数が渡された場合、 `_DllMainCRTStartup` 関数はを呼び出して CRT を初期化する必要があり `_CRT_INIT` ます。 DLL で/GS が使用されている場合、静的初期化子が必要な場合、または MFC または ATL コードのコンテキストで呼び出された場合、この呼び出しだけでは十分ではありません。 詳細については [、「dll および Visual C++ ランタイムライブラリの動作](../../build/run-time-library-behavior.md) 」を参照してください。

## <a name="see-also"></a>関連項目

- [リンカー オプションの設定](../../build/reference/linking.md)
