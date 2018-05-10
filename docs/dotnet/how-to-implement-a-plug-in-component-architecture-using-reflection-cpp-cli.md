---
title: プラグイン アーキテクチャを実装する (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- plug-ins [C++]
- reflection [C++}, plug-ins
ms.assetid: 4f31e42b-78d1-48b9-8fdc-f28c75e8e77e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4e001ef88af0727a994c309d45167787d3e6677b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-a-plug-in-component-architecture-using-reflection-ccli"></a>方法: リフレクションを使用してプラグイン コンポーネント アーキテクチャを実装する (C++/CLI)
次のコード例では、単純な「プラグイン」アーキテクチャを実装するためにリフレクションをデモンストレーションします。 最初のリストは、アプリケーションを 2 番目のプラグイン。 アプリケーションは、コマンドライン引数として提供されるプラグイン DLL 内のフォーム ベースのクラスを使用してそれ自体のメンバーを追加する複数のドキュメント形式です。  
  
 このアプリケーションを使用して、指定されたアセンブリの読み込みを試みます、<xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>メソッドです。 成功すると、アセンブリの内部型は列挙を使用して、<xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName>メソッドです。 各型が使用して、互換性のチェックし、<xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName>メソッドです。 この例では、指定されたアセンブリ内のクラスはから派生した、<xref:System.Windows.Forms.Form>クラスをプラグインとして修飾します。  
  
 互換性のあるクラスがインスタンス化し、<xref:System.Activator.CreateInstance%2A?displayProperty=fullName>を受け入れるメソッド、<xref:System.Type>を引数として、新しいインスタンスにポインターを返します。 それぞれの新しいインスタンスをフォームにアタッチし、表示はします。  
  
 なお、<xref:System.Reflection.Assembly.Load%2A>メソッドは、ファイル拡張子を含むアセンブリ名を受け付けません。 アプリケーションでは、メインの関数は、次のコード例はいずれの場合は、指定された拡張子を削除します。  
  
## <a name="example"></a>例  
 次のコードでは、プラグインを受け入れる、アプリケーションを定義します。アセンブリ名は、最初の引数として指定する必要があります。 このアセンブリは、少なくとも 1 つの公開を含める必要があります<xref:System.Windows.Forms.Form>派生型です。  
  
```  
// plugin_application.cpp  
// compile with: /clr /c  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
  
ref class PluggableForm : public Form  {  
public:  
   PluggableForm() {}  
   PluggableForm(Assembly^ plugAssembly) {  
      Text = "plug-in example";  
      Size = Drawing::Size(400, 400);  
      IsMdiContainer = true;  
  
      array<Type^>^ types = plugAssembly->GetTypes( );  
      Type^ formType = Form::typeid;  
  
      for (int i = 0 ; i < types->Length ; i++) {  
         if (formType->IsAssignableFrom(types[i])) {  
            // Create an instance given the type description.  
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));  
            if (f) {  
               f->Text = types[i]->ToString();  
               f->MdiParent = this;  
               f->Show();  
            }  
         }  
      }  
   }  
};  
  
int main() {  
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");  
   Application::Run(gcnew PluggableForm(a));  
}  
```  
  
## <a name="example"></a>例  
 次のコードから派生した 3 つのクラスを定義する<xref:System.Windows.Forms.Form>です。 実行可能ファイルの前の一覧で、結果として得られるアセンブリの名前が渡されると、これら 3 つのクラスの各が検出され、そうでなかったコンパイル時に、ホスト アプリケーションに認識されているすべてのファクトに関係なく、インスタンス化します。  
  
```  
// plugin_assembly.cpp  
// compile with: /clr /LD  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
using namespace System::Drawing;  
  
public ref class BlueForm : public Form {  
public:  
   BlueForm() {  
      BackColor = Color::Blue;  
   }  
};  
  
public ref class CircleForm : public Form {  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);  
   }  
};  
  
public ref class StarburstForm : public Form {  
public:  
   StarburstForm(){  
      BackColor = Color::Black;  
   }  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      Pen^ p = gcnew Pen(Color::Red, 2);  
      Random^ r = gcnew Random( );  
      Int32 w = ClientSize.Width;  
      Int32 h = ClientSize.Height;  
      for (int i=0; i<100; i++) {  
         float x1 = w / 2;  
         float y1 = h / 2;  
         float x2 = r->Next(w);  
         float y2 = r->Next(h);  
         args->Graphics->DrawLine(p, x1, y1, x2, y2);  
      }  
   }  
};  
```  
  
## <a name="see-also"></a>関連項目  
 [リフレクションの問題 (C++/CLI)](../dotnet/reflection-cpp-cli.md)