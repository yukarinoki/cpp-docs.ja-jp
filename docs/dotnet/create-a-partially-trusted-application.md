---
title: '方法 : 部分信頼されたアプリケーションを作成する (C++/CLI)'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
ms.openlocfilehash: 9df3a751f4073472b9495425599aaf43878db99a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364402"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>方法: CRT ライブラリ DLL との依存関係を削除して部分信頼アプリケーションを作成する

ここでは、msvcm90.dll への依存関係を削除して、Visual C++ を使用して部分的に信頼された共通言語ランタイム アプリケーションを作成する方法について説明します。

**/clr**でビルドされた Visual C++ アプリケーションは、C ランタイム ライブラリの一部である msvcm90.dll に依存します。 アプリケーションを部分信頼環境で使用する場合、CLR は、DLL に特定のコード アクセス セキュリティ規則を適用します。 したがって、msvcm90.dll にはネイティブ コードが含まれ、コード アクセス セキュリティ ポリシーを適用できないため、この依存関係を削除する必要があります。

アプリケーションが C ランタイム ライブラリの機能を使用せず、コードからこのライブラリへの依存関係を削除する場合は **、/NODEFAULTLIB:msvcmrt.lib**リンカー オプションを使用し、ptrustm.lib または ptrustmd.lib とリンクする必要があります。 これらのライブラリには、アプリケーションの初期化と初期化解除のためのオブジェクト ファイル、初期化コードで使用される例外クラス、マネージ例外処理コードが含まれています。 これらのライブラリの 1 つにリンクすると、msvcm90.dll への依存関係が削除されます。

> [!NOTE]
> アセンブリの初期化解除の順序は、ptrust ライブラリを使用するアプリケーションで異なる場合があります。 通常のアプリケーションでは、通常、アセンブリは読み込まれる順序と逆の順序でアンロードされますが、これは保証されません。 部分信頼アプリケーションの場合、通常、アセンブリは読み込まれる順序と同じ順序でアンロードされます。 これは、また、保証されていません。

### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>部分信頼混合 (/clr) アプリケーションを作成するには

1. msvcm90.dll への依存関係を削除するには **、/NODEFAULTLIB:msvcmrt.lib**リンカー オプションを使用して、このライブラリを含めないようにリンカーに指定する必要があります。 Visual Studio 開発環境またはプログラムを使用してこれを行う方法については[、「/NODEFAULTLIB (ライブラリを無視する)」](../build/reference/nodefaultlib-ignore-libraries.md)を参照してください。

1. ptrustm ライブラリの 1 つをリンカー入力の依存関係に追加します。 アプリケーションをリリース モードでビルドする場合は、ptrustm.lib を使用します。 デバッグ モードの場合は、ptrustmd.lib を使用します。 Visual Studio 開発環境またはプログラムを使用してこれを行う方法については、「 [」を参照してください。リンカー入力としてファイルをLib.](../build/reference/dot-lib-files-as-linker-input.md)

## <a name="see-also"></a>関連項目

[混在 (ネイティブおよびマネージド) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[混在アセンブリの初期化](../dotnet/initialization-of-mixed-assemblies.md)<br/>
[混在アセンブリのためのライブラリ サポート](../dotnet/library-support-for-mixed-assemblies.md)<br/>
[/link (リンカーにオプションを渡す)](../build/reference/link-pass-options-to-linker.md)
