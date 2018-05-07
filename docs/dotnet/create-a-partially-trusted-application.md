---
title: '方法: 部分的に信頼されたアプリケーションの作成 (C + + CLI) |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a4a0a4b8b1045a9107158c6e67ecdfa7939b6a08
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>方法: CRT ライブラリ DLL との依存関係を削除して部分信頼アプリケーションを作成する
このトピックでは、Visual C を使用する msvcm90.dll との依存関係を削除することで、部分的に信頼された共通言語ランタイム アプリケーションを作成する方法について説明します。  
  
 作成された Visual C アプリケーション **/clr** C ランタイム ライブラリの一部である msvcm90.dll との依存関係になります。 部分信頼環境で使用するアプリケーションを実行する場合に、CLR には、DLL での特定コード アクセス セキュリティ規則が適用されます。 したがって、msvcm90.dll とにはネイティブ コードが含まれています、それにコード アクセス セキュリティ ポリシーを適用できないために、この依存関係を削除する必要があります。  
  
 使用する必要が場合は、アプリケーションは、C ランタイム ライブラリの機能は使用しないで、コードからこのライブラリへの依存関係を削除するには、**とき**リンカー オプションとリンクします。 これらのライブラリが初期化とアプリケーションの初期化解除用のオブジェクト ファイルを含む、例外クラスは、初期化コードによって使用され、例外処理コードを管理します。 これらのライブラリのいずれかでリンクすると、msvcm90.dll との依存関係が削除されます。  
  
> [!NOTE]
>  Ptrust ライブラリを使用するアプリケーションのアセンブリの初期化解除の順序が異なる場合があります。 標準的なアプリケーション、アセンブリは通常、それらが読み込まれるが、これは保証されませんを逆の順序でアンロードします。 部分信頼アプリケーションでは、アセンブリは読み込まれている順序と同じ順序で通常アンロードします。 これには、または保証されません。  
  
### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>部分的に信頼を作成するには、混合 (/clr) アプリケーション  
  
1.  Msvcm90.dll との依存関係を削除するを使用してこのライブラリを含めないようにリンカーに指定する必要があります、**とき**リンカー オプション。 この操作は、Visual Studio 開発環境を使用またはプログラムで、参照する方法について[/NODEFAULTLIB (ライブラリの無視)](../build/reference/nodefaultlib-ignore-libraries.md)です。  
  
2.  リンカー入力依存関係を ptrustm ライブラリを追加できます。 リリース モードでアプリケーションを構築する場合は、ptrustm.lib を使用します。 デバッグ モードでは、ptrustmd.lib を使用します。 この操作は、Visual Studio 開発環境を使用またはプログラムで、参照する方法について[です。ファイルをリンカー入力として lib](../build/reference/dot-lib-files-as-linker-input.md)です。  
  
## <a name="see-also"></a>関連項目  
 [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)   
 [混在アセンブリの初期化](../dotnet/initialization-of-mixed-assemblies.md)   
 [混在アセンブリのライブラリのサポート](../dotnet/library-support-for-mixed-assemblies.md)   
 [/link (リンカーにオプションを渡す)](../build/reference/link-pass-options-to-linker.md)   
