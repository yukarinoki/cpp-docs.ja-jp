---
title: '方法: Windows レジストリにデータを書き込む (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- registry, writing to
- Visual C++, writing to Windows Registry
ms.assetid: 3d40b978-4baa-4779-bfe3-47e2917b757f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 304bc224be8776c9793af07283c6a5697a4e49eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-data-to-the-windows-registry-ccli"></a>方法: Windows レジストリにデータを書き込む (C++/CLI)
次のコード例では、<xref:Microsoft.Win32.Registry.CurrentUser>の書き込み可能インスタンスを作成するキー、<xref:Microsoft.Win32.RegistryKey>に対応するクラス、**ソフトウェア**キー。 その後、<xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A> メソッドを使用して、新しいキーを作成し、キーと値のペアを追加します。  
  
## <a name="example"></a>例  
  
### <a name="code"></a>コード  
  
```  
// registry_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main()  
{  
   // The second OpenSubKey argument indicates that  
   // the subkey should be writable.   
   RegistryKey^ rk;  
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);  
   if (!rk)  
   {  
      Console::WriteLine("Failed to open CurrentUser/Software key");  
      return -1;  
   }  
  
   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");  
   if (!nk)  
   {  
      Console::WriteLine("Failed to create 'NewRegKey'");  
      return -1;  
   }  
  
   String^ newValue = "NewValue";  
   try  
   {  
      nk->SetValue("NewKey", newValue);  
      nk->SetValue("NewKey2", 44);  
   }  
   catch (Exception^)  
   {  
      Console::WriteLine("Failed to set new values in 'NewRegKey'");  
      return -1;  
   }  
  
   Console::WriteLine("New key created.");  
   Console::Write("Use REGEDIT.EXE to verify ");  
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");  
   return 0;  
}  
```  
  
## <a name="remarks"></a>コメント  
 レジストリにアクセスする .NET Framework を使用して、<xref:Microsoft.Win32.Registry>と[RegistryKey](https://msdn.microsoft.com/en-us/library/microsoft.win32.registrykey.aspx)はどちらもクラスで定義、<xref:Microsoft.Win32>名前空間。 **レジストリ**クラスの静的インスタンスのコンテナーが、<xref:Microsoft.Win32.RegistryKey>クラスです。 各インスタンスは、ルート レジストリ ノードを表します。 インスタンスは、<xref:Microsoft.Win32.Registry.ClassesRoot>、<xref:Microsoft.Win32.Registry.CurrentConfig>、<xref:Microsoft.Win32.Registry.CurrentUser>、<xref:Microsoft.Win32.Registry.LocalMachine>、および <xref:Microsoft.Win32.Registry.Users> です。  
  
## <a name="see-also"></a>関連項目  
 [方法: Windows レジストリからデータを読み取る (C + + CLI)](../dotnet/how-to-read-data-from-the-windows-registry-cpp-cli.md)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)