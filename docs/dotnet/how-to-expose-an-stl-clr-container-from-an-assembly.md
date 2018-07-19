---
title: '方法: アセンブリから STL/CLR コンテナーである公開 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, cross-assembly issues
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 58edb96d3947cc5694731d78c6aa71a855ef7aa9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33140174"
---
# <a name="how-to-expose-an-stlclr-container-from-an-assembly"></a>方法: アセンブリから STL/CLR コンテナーを公開する
などの STL/CLR コンテナー`list`と`map`テンプレート ref クラスとして実装されます。 C++ テンプレート、コンパイル時にインスタンス化されているために、正確に同じシグネチャが異なるアセンブリにある 2 つのテンプレート クラスは、実際にはさまざまな種類になります。 つまり、テンプレート クラスは、アセンブリ境界を越えて使用できません。  
  
 STL/CLR コンテナーがジェネリック インターフェイスを実装するのには、アセンブリ間の共有可能な<xref:System.Collections.Generic.ICollection%601>です。 このジェネリック インターフェイスを使用すると、C++、c#、および Visual Basic の場合など、ジェネリックをサポートするすべての言語は STL/CLR コンテナーにアクセスできます。  
  
 このトピックは、という名前の C++ アセンブリで記述された複数の STL/CLR コンテナーの要素を表示する方法を示します`StlClrClassLibrary`です。 2 つのアセンブリへのアクセスを示します`StlClrClassLibrary`です。 C++、および C# の場合、2 つ目では、最初のアセンブリが書き込まれます。  
  
 使用して、コンテナーのジェネリック インターフェイスを表示できる場合、両方のアセンブリは、C++ で記述されて、その`generic_container`typedef です。 たとえば、次の種類のコンテナーがある`cliext::vector<int>`、そのジェネリック インターフェイスは、: `cliext::vector<int>::generic_container`。 使用して同様に、ジェネリック インターフェイス経由で、反復子を取得することができます、`generic_iterator`に示すように、typedef:`cliext::vector<int>::generic_iterator`です。  
  
 これらの typedefs は、C++ ヘッダー ファイルで宣言され、以降の他の言語で記述されたアセンブリと使用できません。 したがって、ジェネリック インターフェイスにアクセスする`cliext::vector<int>`(C#) またはその他の任意の .NET 言語で使用`System.Collections.Generic.ICollection<int>`です。 このコレクションを反復処理に使用して、`foreach`ループします。  
  
 次の表に、各 STL/CLR コンテナーを実装するジェネリック インターフェイスを示します。  
  
|STL/CLR コンテナー|ジェネリック インターフェイス|  
|------------------------|-----------------------|  
|deque < T\>|ICollection < T\>|  
|hash_map < K, V >|IDictionary < K, V >|  
|hash_multimap < K, V >|IDictionary < K, V >|  
|hash_multiset < T\>|ICollection < T\>|  
|hash_set < T\>|ICollection < T\>|  
|リスト < T\>|ICollection < T\>|  
|< K, V > のマップ|IDictionary < K, V >|  
|multimap < K, V >|IDictionary < K, V >|  
|multiset < T\>|ICollection < T\>|  
|設定 < T\>|ICollection < T\>|  
|vector < T\>|ICollection < T\>|  
  
> [!NOTE]
>  `queue`、 `priority_queue`、および`stack`反復子をサポートしていないコンテナーは、ジェネリック インターフェイスを実装しないアセンブリ間のアクセスをすることはできません。  
  
## <a name="example-1"></a>例 1  
  
### <a name="description"></a>説明  
 この例では、プライベート STL/CLR メンバー データを含む C++ クラスを宣言します。 クラスのプライベート コレクションへのアクセスを許可するパブリック メソッドを宣言できます。 2 つの方法で、C++ クライアントのいずれかおよびその他の .NET クライアントのいずれかを行います。  
  
### <a name="code"></a>コード  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="example-2"></a>例 2  
  
### <a name="description"></a>説明  
 この例では、例 1 で宣言されたクラスを実装します。 マニフェスト ツールを使用してクライアントがこのクラス ライブラリを使用するためには、 **mt.exe** DLL にマニフェスト ファイルを埋め込む。 詳細については、コードのコメントを参照してください。  
  
 マニフェスト ツールとサイド バイ サイド アセンブリの詳細については、次を参照してください。 [c/c++ 分離アプリケーションの構築とサイド バイ サイド アセンブリ](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)です。  
  
### <a name="code"></a>コード  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## <a name="example-3"></a>例 3  
  
### <a name="description"></a>説明  
 この例では、例 1 および 2 で作成したクラス ライブラリを使用する C++ クライアントを作成します。 このクライアントを使用して、`generic_container`コンテナーを反復処理して、その内容を表示する STL/CLR コンテナーの typedef。  
  
### <a name="code"></a>コード  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### <a name="output"></a>出力  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
## <a name="example-4"></a>例 4  
  
### <a name="description"></a>説明  
 この例では、例 1 および 2 で作成したクラス ライブラリを使用する c# クライアントを作成します。 このクライアントを使用して、 <xref:System.Collections.Generic.ICollection%601> STL/CLR コンテナーの内容を表示して、コンテナーを反復処理するメソッド。  
  
### <a name="code"></a>コード  
  
```  
// CsConsoleApp.cs  
// compile with: /r:Microsoft.VisualC.STLCLR.dll /r:StlClrClassLibrary.dll /r:System.dll  
  
using System;  
using System.Collections.Generic;  
using StlClrClassLibrary;  
using cliext;  
  
namespace CsConsoleApp  
{  
    class Program  
    {  
        static int Main(string[] args)  
        {  
            StlClrClass theClass = new StlClrClass();  
  
            Console.WriteLine("cliext::deque contents:");  
            ICollection<char> iCollChar = theClass.GetDequeCs();  
            foreach (char c in iCollChar)  
            {  
                Console.WriteLine(c);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::list contents:");  
            ICollection<float> iCollFloat = theClass.GetListCs();  
            foreach (float f in iCollFloat)  
            {  
                Console.WriteLine(f);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::map contents:");  
            IDictionary<int, string> iDict = theClass.GetMapCs();  
            foreach (KeyValuePair<int, string> kvp in iDict)  
            {  
                Console.WriteLine("{0} {1}", kvp.Key, kvp.Value);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::set contents:");  
            ICollection<double> iCollDouble = theClass.GetSetCs();  
            foreach (double d in iCollDouble)  
            {  
                Console.WriteLine(d);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::vector contents:");  
            ICollection<int> iCollInt = theClass.GetVectorCs();  
            foreach (int i in iCollInt)  
            {  
                Console.WriteLine(i);  
            }  
            Console.WriteLine();  
  
            return 0;  
        }  
    }  
}  
```  
  
### <a name="output"></a>出力  
  
```  
cliext::deque contents:  
a  
b  
  
cliext::list contents:  
3.14159  
2.71828  
  
cliext::map contents:  
0 Hello  
1 World  
  
cliext::set contents:  
2.71828  
3.14159  
  
cliext::vector contents:  
10  
20  
```  
  
## <a name="see-also"></a>関連項目  
 [STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)