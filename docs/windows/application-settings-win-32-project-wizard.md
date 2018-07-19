---
title: アプリケーション設定、Win32 プロジェクト ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.appwiz.win32.appset
dev_langs:
- C++
helpviewer_keywords:
- application settings [C++]
- Win32 Project Wizard, application settings
ms.assetid: d6b818f0-9b23-4793-a6c5-df1c8c594bad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 55ae50d849a67da69cde6a9c4b1529c34ee4b428
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860061"
---
# <a name="application-settings-win-32-project-wizard"></a>[アプリケーションの設定] (Win32 アプリケーション ウィザード)
ウィザードのこのページを使用して、Win32 プロジェクトのオプションを設定します。  
  
 **アプリケーションの種類**  
 指定したタイプのアプリケーションが作成されます。  
  
|オプション|説明|  
|------------|-----------------|  
|**コンソール アプリケーション**|コンソール アプリケーションを作成します。 コンソール プログラムがで開発した[コンソール関数](https://msdn.microsoft.com/en-us/library/ms813137.aspx)、コンソール ウィンドウでキャラクター モードのサポートを提供します。 Visual C[ランタイム ライブラリ](../c-runtime-library/c-run-time-library-reference.md)も出力を提供しなどの標準の入出力関数を使ってコンソール ウィンドウから入力**printf_s()** と**scanf_s()** です。 コンソール アプリケーションにはグラフィカル ユーザー インターフェイスはありません。 コンパイルによって .exe ファイルが生成され、コマンド ラインからスタンドアロン アプリケーションとして実行できます。<br /><br /> コンソール アプリケーションには MFC サポートや ATL サポートを追加できます。|  
|**Windows アプリケーション**|Win32 プログラムが作成されます。 Win32 プログラムとは C または C++ で記述された実行可能アプリケーション (EXE) であり、Win32 API を呼び出してグラフィカル ユーザー インターフェイスを作成します。<br /><br /> Windows アプリケーションには MFC サポートや ATL サポートを追加できません。|  
|**DLL**|Win32 ダイナミック リンク ライブラリ (DLL: Dynamic-Link Library) が作成されます。 Win32 DLL とは C または C++ で記述されたバイナリ ファイルであり、MFC クラスではなく Win32 API を呼び出したり、複数のアプリケーションで同時に使用できる関数の共有ライブラリとして機能します。<br /><br /> DLL アプリケーションには MFC サポートや ATL サポートを追加できません。 DLL がシンボルをエクスポートするように指定できます。|  
|**スタティック ライブラリ**|スタティック ライブラリが作成されます。 スタティック ライブラリとは、実行可能ファイルの作成時にプログラムにリンクされるオブジェクト、およびそのオブジェクトの関数とデータを含むファイルです。 スターター ファイルを作成する方法を説明し、[プロジェクト プロパティ](../ide/property-pages-visual-cpp.md)スタティック ライブラリ。 スタティック ライブラリ ファイルには以下の利点があります。<br /><br /> は、Win32 スタティック ライブラリで作業しているアプリケーションは MFC クラスではなく Win32 API に呼び出しを行う場合に便利です。<br />-リンク プロセスは、C または C++ では、Windows アプリケーションの残りの部分が書き込まれるかどうかは同じです。<br />スタティック ライブラリは、MFC ベースのプログラムまたは非 MFC プログラム-リンクできます。|  
  
 **追加オプション**  
 アプリケーションのサポートとオプションを定義します。定義内容はアプリケーションの種類によって異なります。  
  
|オプション|説明|  
|------------|-----------------|  
|**空のプロジェクト**|プロジェクト ファイルは空白にします。 一連のソース コード ファイル (.cpp ファイル、ヘッダー ファイル、アイコン、ツール バー、ダイアログ ボックスなど) があり、Visual C++ 開発環境でプロジェクトを作成する場合は、最初に空のプロジェクトを作成してから、そのプロジェクトにファイルを追加する必要があります。<br /><br /> このオプションはスタティック ライブラリ プロジェクトには使用できません。|  
|**シンボルのエクスポート**|DLL プロジェクトがシンボルをエクスポートするように指定します。|  
|**プリコンパイル済みヘッダー**|スタティック ライブラリ プロジェクトでプリコンパイル済みヘッダーを使用するように指定します。|  
|Security Development Lifecycle (SDL) チェック(C)|SDL の詳細については、次を参照してください[Microsoft Security Development Lifecycle (SDL) のプロセス ガイダンス。](../build/reference/sdl-enable-additional-security-checks.md)|  
  
 **サポートを追加します。**  
 Visual C++ に用意されているライブラリの 1 つに対するサポートを追加します。  
  
|オプション|説明|  
|------------|-----------------|  
|**ATL**|ATL (Active Template Library) のクラスのサポートがプロジェクトに組み込まれます。 このオプションを使用できるのは、Win32 コンソール アプリケーションだけです。<br /><br /> **注**は、このオプションは、ATL を使用して ATL オブジェクト ウィザードのコードを追加するためのサポートを示しません。 ATL オブジェクトを追加できるのは、ATL プロジェクト、または ATL サポートを含む MFC プロジェクトだけです。|  
|**MFC**|MFC (Microsoft Foundation Class) ライブラリのサポートがプロジェクトに組み込まれます。 このオプションを使用できるのは、Win32 コンソール アプリケーションとスタティック ライブラリだけです。|  
  
## <a name="see-also"></a>関連項目  
 [Win32 アプリケーション ウィザード](../windows/win32-application-wizard.md)   
