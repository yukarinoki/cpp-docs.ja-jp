---
title: '方法: 診断し、アセンブリの互換性の問題を修正 (C + + CLI) |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- versioning, diagnosing conflicts
- versioning
- exceptions, diagnosing odd behavior
- compatibility, between assemblies
ms.assetid: 297c71e3-04a8-4d24-a5dc-b04a2c5cc6fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4440ab455aff8922c108cdb35cff041cd67f56d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133428"
---
# <a name="how-to-diagnose-and-fix-assembly-compatibility-problems-ccli"></a>方法: アセンブリの互換性の問題を診断し修復する (C++/CLI)
このトピックでは、コンパイル時に参照されるアセンブリのバージョン、実行時に参照されるアセンブリのバージョンが一致しない場合の動作について説明しますと、問題を回避する方法です。  
  
 その他のアセンブリを参照するアセンブリがコンパイルされるときに、`#using`構文です。 コンパイル時に、これらのアセンブリは、コンパイラによってアクセスします。 これらのアセンブリからの情報は、最適化の決定に使用されます。  
  
 ただし、参照アセンブリが変更され、再コンパイルがそれに依存する参照元のアセンブリが再コンパイルされない場合は、アセンブリできないか、互換性のあるものです。 最適化の判断で有効だった最初できないアセンブリの新しいバージョンに対して正しく。 これらの非互換性によるさまざまなのランタイム エラーが発生する可能性があります。 このような場合に生成される特定の例外ではありません。 実行時に、エラーが報告される方法は、問題の原因となったコードの変更の性質によって異なります。  
  
 アプリケーション全体が、製品のリリース バージョンの再構築された場合に限り、これらのエラーは、最終的な実稼働コードで問題をしないでください。 パブリックにリリースされるアセンブリは、正式なバージョン番号、これらの問題を回避することを確認してくださいでマークする必要があります。 詳細については、「[アセンブリのバージョン管理](/dotnet/framework/app-domains/assembly-versioning)」を参照してください。  
  
### <a name="diagnosing-and-fixing-an-incompatibility-error"></a>診断および非互換性エラーを修正  
  
1.  ランタイム例外または別のアセンブリを参照するコードで発生する他のエラー状況が発生して他の原因がある場合、古いアセンブリを含むを扱うこと可能性があります。  
  
2.  最初に、特定し、例外またはその他のエラー状態を再現します。 期限切れの例外のために発生する問題を再現可能にする必要があります。  
  
3.  アプリケーションで参照されるアセンブリのタイムスタンプを確認してください。  
  
4.  参照先アセンブリのタイムスタンプが、アプリケーションの前回のコンパイルのタイムスタンプより後の場合は、アプリケーションが古すぎます。 この場合、最新のアセンブリを使用してアプリケーションを再コンパイルし、必要なコード変更します。  
  
5.  アプリケーションを再実行して、問題を再現し、例外が発生しないことを確認する手順に従います。  
  
## <a name="example"></a>例  
 次のプログラムは、メソッドのアクセシビリティを削減し、再コンパイルしなくても、別のアセンブリには、そのメソッドにアクセスしようとして問題を示しています。 コンパイルしてみてください`changeaccess.cpp`最初。 これは、参照アセンブリが変更されます。 コンパイルし、`referencing.cpp`です。 コンパイルは成功します。 ここで、呼び出されたメソッドのアクセシビリティを削減します。 再コンパイル`changeaccess.cpp`フラグ`/DCHANGE_ACCESS`です。 これにより、メソッド、プライベートではなく、保護されたなった呼び出すことができます法的ようにします。 再コンパイルせず`referencing.exe`アプリケーションを再実行します。 例外<xref:System.MethodAccessException>になります。  
  
```  
// changeaccess.cpp  
// compile with: /clr:safe /LD  
// After the initial compilation, add /DCHANGE_ACCESS and rerun  
// referencing.exe to introduce an error at runtime. To correct  
// the problem, recompile referencing.exe  
  
public ref class Test {  
#if defined(CHANGE_ACCESS)  
protected:  
#else  
public:  
#endif  
  
  int access_me() {  
    return 0;  
  }  
  
};  
  
```  
  
```  
// referencing.cpp  
// compile with: /clr:safe   
#using <changeaccess.dll>  
  
// Force the function to be inline, to override the compiler's own  
// algorithm.  
__forceinline  
int CallMethod(Test^ t) {  
  // The call is allowed only if access_me is declared public  
  return t->access_me();  
}  
  
int main() {  
  Test^ t = gcnew Test();  
  try  
  {  
    CallMethod(t);  
    System::Console::WriteLine("No exception.");  
  }  
  catch (System::Exception ^ e)  
  {  
    System::Console::WriteLine("Exception!");  
  }  
  return 0;  
}  
  
```  
  
## <a name="see-also"></a>関連項目  
 [#using ディレクティブ](../preprocessor/hash-using-directive-cpp.md)   
 [マネージ型 (C++/CLI)](../dotnet/managed-types-cpp-cli.md)