---
title: GetProcAddress
ms.date: 11/04/2016
f1_keywords:
- GetProcAddress
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
ms.openlocfilehash: 5ee985da29e38bfb262c72315a57c0b588b2e82e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188978"
---
# <a name="getprocaddress"></a>GetProcAddress

明示的にリンクする DLL の呼び出しプロセス[GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) DLL でエクスポートされた関数のアドレスを取得します。 返された関数ポインターを使って、DLL 関数を呼び出します。 **GetProcAddress** DLL モジュール ハンドルをパラメーターとして受け取り (いずれかによって返される**LoadLibrary**、 `AfxLoadLibrary`、または**GetModuleHandle**) と関数のいずれかの名前を受け取ります呼び出し、関数のエクスポート序数。

DLL 関数の呼び出しにはポインターが使われ、コンパイル時にデータ型はチェックされないため、関数へ渡すパラメーターが正しいことを確認してください。パラメーターが不正な場合、スタック上に割り当てられたメモリ域をオーバーしたり、アクセス違反を起こしたりすることがあります。 型をタイプセーフにする 1 つの方法は、エクスポート関数の関数プロトタイプを見て、関数ポインター用に対応する typedef を作成することです。 例:

```
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);
...

HINSTANCE hDLL;               // Handle to DLL
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer
DWORD dwParam1;
UINT  uParam2, uReturnVal;

hDLL = LoadLibrary("MyDLL");
if (hDLL != NULL)
{
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,
                                           "DLLFunc1");
   if (!lpfnDllFunc1)
   {
      // handle the error
      FreeLibrary(hDLL);
      return SOME_ERROR_CODE;
   }
   else
   {
      // call the function
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);
   }
}
```

呼び出すときに関数を指定する方法**GetProcAddress** DLL がどのように構築されたかによって異なります。

モジュール定義 (.def) ファイルにリンクする DLL が組み込まれている場合、および序数がの関数と表示されている場合のみ、エクスポート序数を取得できます、**エクスポート**DLL の .def ファイルのセクション。 呼び出す**GetProcAddress**とエクスポートは、関数名ではなく、序数がエクスポート序数が dll のインデックス テーブルのエクスポートを配信するため、DLL によってエクスポートされた関数の多くがある場合に若干速くなります。 エクスポート序数**GetProcAddress** DLL のエクスポート テーブル内の関数名を指定した名前を比較するのではなく、直接関数を見つけることができます。 ただし、呼び出す必要があります**GetProcAddress** .def ファイルにエクスポートされた関数への序数の割り当てを制御している場合にのみ、エクスポート序数。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#linking-implicitly)

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [LoadLibrary と AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)

- [DEF ファイルを使った DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)

## <a name="see-also"></a>関連項目

[Visual C++ の DLL](dlls-in-visual-cpp.md)
