---
title: '方法: Windows レジストリからデータを読み取る (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, reading from Windows Registry
- registry, reading
ms.assetid: aebf52c0-acc7-40e2-adbc-d34e0a1e467e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 87c882bcf2a7900e1f95ea968407c159333c6cb2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132555"
---
# <a name="how-to-read-data-from-the-windows-registry-ccli"></a>方法: Windows レジストリからデータを読み込む (C++/CLI)
<xref:Microsoft.Win32.Registry.CurrentUser> キーを使用して、Windows レジストリからデータを読み込む方法を次のコード例に示します。 最初に、サブキーが列挙を使用して、<xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A>メソッドし Identities サブキーを使用してを開くが、<xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A>メソッドです。 ルート キー同様、各サブキーは <xref:Microsoft.Win32.RegistryKey> クラスで表されます。 最後に、新しい <xref:Microsoft.Win32.RegistryKey> オブジェクトを使用してキーと値のペアが一覧表示されます。  
  
## <a name="example"></a>例  
  
### <a name="code"></a>コード  
  
```  
// registry_read.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main( )  
{  
   array<String^>^ key = Registry::CurrentUser->GetSubKeyNames( );  
  
   Console::WriteLine("Subkeys within CurrentUser root key:");  
   for (int i=0; i<key->Length; i++)  
   {  
      Console::WriteLine("   {0}", key[i]);  
   }  
  
   Console::WriteLine("Opening subkey 'Identities'...");  
   RegistryKey^ rk = nullptr;  
   rk = Registry::CurrentUser->OpenSubKey("Identities");  
   if (rk==nullptr)  
   {  
      Console::WriteLine("Registry key not found - aborting");  
      return -1;  
   }  
  
   Console::WriteLine("Key/value pairs within 'Identities' key:");  
   array<String^>^ name = rk->GetValueNames( );  
   for (int i=0; i<name->Length; i++)  
   {  
      String^ value = rk->GetValue(name[i])->ToString();  
      Console::WriteLine("   {0} = {1}", name[i], value);  
   }  
  
   return 0;  
}  
```  
  
## <a name="remarks"></a>コメント  
 <xref:Microsoft.Win32.Registry> クラスは、<xref:Microsoft.Win32.RegistryKey> の静的インスタンスの単なるコンテナーです。 各インスタンスは、ルート レジストリ ノードを表します。 インスタンスは、<xref:Microsoft.Win32.Registry.ClassesRoot>、<xref:Microsoft.Win32.Registry.CurrentConfig>、<xref:Microsoft.Win32.Registry.CurrentUser>、<xref:Microsoft.Win32.Registry.LocalMachine>、および <xref:Microsoft.Win32.Registry.Users> です。  
  
 <xref:Microsoft.Win32.Registry> クラスのオブジェクトは、静的オブジェクトであるだけでなく、読み取り専用です。 さらに、レジストリ オブジェクトのコンテンツにアクセスするために作成される <xref:Microsoft.Win32.RegistryKey> クラスのインスタンスも読み取り専用です。 この動作をオーバーライドする方法の例は、次を参照してください。[する方法: Windows レジストリにデータを書き込む (C + + CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)です。  
  
 <xref:Microsoft.Win32.Registry> クラスには、さらに <xref:Microsoft.Win32.Registry.DynData> と <xref:Microsoft.Win32.Registry.PerformanceData> の 2 つのオブジェクトがあります。 この 2 つのオブジェクトは両方とも <xref:Microsoft.Win32.RegistryKey> クラスのインスタンスです。 <xref:Microsoft.Win32.Registry.DynData>オブジェクトには、Windows 98 や Windows me でのみサポートされている動的レジストリ情報が含まれています。 <xref:Microsoft.Win32.Registry.PerformanceData> オブジェクトを使用すると、Windows パフォーマンス モニター システムを使用するアプリケーションのパフォーマンス カウンター情報にアクセスできます。 <xref:Microsoft.Win32.Registry.PerformanceData>ノードが表す情報をレジストリに実際に格納されていないと、そのため、Regedit.exe を使用すると表示することはできません。  
  
## <a name="see-also"></a>関連項目  
 [方法: Windows レジストリにデータを書き込む (C + + CLI)](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)   
 [Windows の操作 (C + + CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)