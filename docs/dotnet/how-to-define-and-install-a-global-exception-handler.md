---
title: '方法: グローバル例外ハンドラーを定義およびインストールする'
ms.date: 11/04/2016
helpviewer_keywords:
- handlers, global
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
ms.openlocfilehash: 27666702a548c0c71b7e25597a1927520968b124
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544977"
---
# <a name="how-to-define-and-install-a-global-exception-handler"></a>方法: グローバル例外ハンドラーを定義およびインストールする

次のコード例は、未処理の例外をキャプチャする方法を示しています。 この例のフォームには、押されたときに null 参照が実行され、例外がスローされるボタンが含まれています。 この機能は、一般的なコードエラーを表します。 結果の例外は、main 関数によってインストールされたアプリケーション全体の例外ハンドラーによってキャッチされます。

これは、デリゲートを <xref:System.Windows.Forms.Application.ThreadException> イベントにバインドすることで実現されます。 この場合、後続の例外は `App::OnUnhandled` メソッドに送信されます。

## <a name="example"></a>例

```cpp
// global_exception_handler.cpp
// compile with: /clr
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Threading;
using namespace System::Drawing;
using namespace System::Windows::Forms;

ref class MyForm : public Form
{
   Button^ b;
public:
   MyForm( )
   {
      b = gcnew Button( );
      b->Text = "Do Null Access";
      b->Size = Drawing::Size(150, 30);
      b->Click += gcnew EventHandler(this, &MyForm::OnClick);
      Controls->Add(b);
   }
   void OnClick(Object^ sender, EventArgs^ args)
   {
      // do something illegal, like call through a null pointer...
      Object^ o = nullptr;
      o->ToString( );
   }
};

ref class App
{
public:
   static void OnUnhandled(Object^ sender, ThreadExceptionEventArgs^ e)
   {
      MessageBox::Show(e->Exception->Message, "Global Exeception");
      Application::ExitThread( );
   }
};

int main()
{
   Application::ThreadException += gcnew
      ThreadExceptionEventHandler(App::OnUnhandled);

   MyForm^ form = gcnew MyForm( );
   Application::Run(form);
}
```

## <a name="see-also"></a>参照

[例外処理](../extensions/exception-handling-cpp-component-extensions.md)
