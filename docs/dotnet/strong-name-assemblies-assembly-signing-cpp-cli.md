---
title: 厳密名アセンブリ (アセンブリ署名) (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d7ae911d2572a35ee8dbb21d5484b4679b64c4d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>厳密名アセンブリ (アセンブリ署名) (C++/CLI)
このトピックでは、アセンブリに厳密な名前を付けるとも呼ば、アセンブリに署名する方法について説明します。  
  
## <a name="remarks"></a>コメント  
 Visual C を使用する場合は、アセンブリの署名の CLR 属性に関連する問題を回避するアセンブリに署名するリンカー オプションを使用します。  
  
-   <xref:System.Reflection.AssemblyDelaySignAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyFileAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 属性を使用しない理由には、キー名がアセンブリのメタデータは、セキュリティ リスクとなることができます、ファイル名には、機密情報が含まれている場合に表示されているファクトが含まれます。 また、Visual C 開発環境で使用されるビルド プロセスには、アセンブリに署名されている CLR 属性を使用して、アセンブリに厳密な名前を指定し、アセンブリで mt.exe などに処理後のツールを実行すると、キーが無効になります。  
  
 コマンドラインでビルド、リンカー オプションを使用して、アセンブリに署名、処理後のツール (mt.exe) などを実行するとは、sn.exe を使用してアセンブリを再署名する必要があります。 または、ビルド、遅延署名アセンブリし、処理後のツールを実行した後、署名を完了します。  
  
 正常に sn.exe を明示的に呼び出すことによってアセンブリに署名することができます、開発環境でのビルド時に署名の属性を使用する場合 ([Sn.exe (厳密名ツール)](/dotnet/framework/tools/sn-exe-strong-name-tool)) のビルド後イベントにします。 詳細については、次を参照してください。[ビルド イベントの指定](../ide/specifying-build-events.md)です。 ビルド時間が小さい属性およびリンカー オプションを使用すると比較して、ビルド後のイベントを使用する場合あります。  
  
 次のリンカー オプションは、アセンブリの署名をサポートします。  
  
-   [/DELAYSIGN (アセンブリの部分署名)](../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/KEYFILE (アセンブリに署名するためのキーまたはキー ペアの指定)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/KEYCONTAINER (アセンブリに署名するためのキー コンテナーの指定)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 厳密なアセンブリの詳細については、次を参照してください。[作成と使用](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)です。  
  
## <a name="see-also"></a>関連項目  
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)