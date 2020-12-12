---
description: '詳細については、「方法: CRT ライブラリ DLL の依存関係を削除して部分信頼アプリケーションを作成する」を参照してください。'
title: '方法: 部分的に信頼されたアプリケーションを作成する (C++/CLI)'
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
ms.openlocfilehash: 937262595df4415d5620b60d9ccd8c17a6c44abf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124281"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>方法: CRT ライブラリ DLL との依存関係を削除して部分信頼アプリケーションを作成する

このトピックでは、msvcm90.dll の依存関係を削除して、Visual C++ を使用して部分的に信頼された共通言語ランタイムアプリケーションを作成する方法について説明します。

**/Clr** でビルドされた Visual C++ アプリケーションは、C ランタイムライブラリの一部である msvcm90.dll に依存します。 アプリケーションを部分信頼環境で使用する場合、CLR は DLL に特定のコードアクセスセキュリティ規則を適用します。 このため、この依存関係を削除する必要があります。 msvcm90.dll にネイティブコードが含まれており、コードアクセスセキュリティポリシーを適用できないためです。

アプリケーションが C ランタイムライブラリの機能を使用せず、コードからこのライブラリの依存関係を削除する場合は、 **/NODEFAULTLIB: msvcmrt.lib** リンカーオプションを使用して、ptrustm .lib または ptrustm. lib とリンクする必要があります。 これらのライブラリには、アプリケーションの初期化と初期化解除中のためのオブジェクトファイル、初期化コードによって使用される例外クラス、およびマネージ例外処理コードが含まれています。 これらのライブラリのいずれかでリンクすると、msvcm90.dll の依存関係がすべて削除されます。

> [!NOTE]
> アセンブリ初期化解除中の順序は、ptrust ライブラリを使用するアプリケーションによって異なる場合があります。 通常のアプリケーションでは、通常、アセンブリは読み込まれた逆の順序でアンロードされますが、これは保証されません。 部分信頼アプリケーションでは、通常、アセンブリは読み込まれた順序と同じ順序でアンロードされます。 これも保証されていません。

### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>部分的に信頼された混合 (/clr) アプリケーションを作成するには

1. msvcm90.dll の依存関係を削除するには、 **/NODEFAULTLIB: msvcmrt.lib** リンカーオプションを使用して、このライブラリをインクルードしないようにリンカーに指定する必要があります。 Visual Studio 開発環境またはプログラムを使用してこれを行う方法については、「 [/NODEFAULTLIB (ライブラリを無視する)](../build/reference/nodefaultlib-ignore-libraries.md)」を参照してください。

1. リンカー入力の依存関係に、いずれかの ptrustm ライブラリを追加します。 リリースモードでアプリケーションをビルドする場合は、ptrustm .lib を使用します。 デバッグモードの場合は、ptrustmd を使用します。 Visual Studio 開発環境またはプログラムを使用してこれを行う方法については、「」を参照してください [。リンカー入力としての Lib ファイル](../build/reference/dot-lib-files-as-linker-input.md)。

## <a name="see-also"></a>関連項目

[混合 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[混合アセンブリの初期化](../dotnet/initialization-of-mixed-assemblies.md)<br/>
[ライブラリによる混合アセンブリのサポート](../dotnet/library-support-for-mixed-assemblies.md)<br/>
[/link (リンカーにオプションを渡す)](../build/reference/link-pass-options-to-linker.md)
