---
description: '詳細情報: 厳密名アセンブリ (アセンブリ署名) (C++/CLI)'
title: 厳密名アセンブリ (アセンブリ署名) (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- assemblies [C++]
- signing assemblies
- .NET Framework [C++], assembly signing
- assemblies [C++], signing
- linker [C++], assembly signing
- strong-named assemblies [C++]
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
ms.openlocfilehash: 9fc08df759fa384ed13dbe3d8c3eb2d843183517
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335309"
---
# <a name="strong-name-assemblies-assembly-signing-ccli"></a>厳密名アセンブリ (アセンブリ署名) (C++/CLI)

このトピックでは、アセンブリに署名する方法について説明します。多くの場合、アセンブリに厳密な名前を付けることを指します。

## <a name="remarks"></a>解説

Visual C++ を使用する場合は、アセンブリに署名するためにリンカーオプションを使用して、アセンブリ署名の CLR 属性に関連する問題を回避します。

- <xref:System.Reflection.AssemblyDelaySignAttribute>

- <xref:System.Reflection.AssemblyKeyFileAttribute>

- <xref:System.Reflection.AssemblyKeyNameAttribute>

属性を使用しない理由として、キー名がアセンブリメタデータに表示されることがあります。これは、ファイル名に機密情報が含まれている場合、セキュリティ上のリスクになる可能性があります。 また、CLR 属性を使用してアセンブリに厳密な名前を付け、アセンブリに対して mt.exe のような後処理ツールを実行すると、Visual C++ 開発環境で使用されるビルドプロセスによって、アセンブリに署名されたキーが無効になります。

コマンドラインでビルドする場合は、リンカーオプションを使用してアセンブリに署名した後、処理後のツール (mt.exe など) を実行し、sn.exe でアセンブリに再署名する必要があります。 または、アセンブリをビルドして遅延署名し、後処理ツールを実行した後に署名を完了することもできます。

開発環境でビルドするときに署名属性を使用する場合は、ビルド後のイベントで sn.exe ([Sn.exe (厳密名)](/dotnet/framework/tools/sn-exe-strong-name-tool))) を明示的に呼び出すことによって、アセンブリに正常に署名できます。 詳細については、「[ビルド イベントの指定](../build/specifying-build-events.md)」を参照してください。 リンカーオプションを使用する場合と比較して、属性とビルド後のイベントを使用する場合、ビルド時間が短くなることがあります。

次のリンカーオプションは、アセンブリの署名をサポートしています。

- [/DELAYSIGN (アセンブリの部分署名)](../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYFILE (アセンブリに署名するためのキーまたはキーペアの指定)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER (アセンブリに署名するためのキーコンテナーの指定)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

厳密なアセンブリの詳細については、「 [Strong-Named アセンブリの作成と使用](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)」を参照してください。

## <a name="see-also"></a>関連項目

[C++/CLI を使用した .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
