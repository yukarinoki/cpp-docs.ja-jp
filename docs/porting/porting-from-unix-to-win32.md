---
title: UNIX から Win32 への移植 | Microsoft Docs
ms.custom: ''
ms.date: 08/02/2018
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- APIs [C++], porting to Win32
- Windows API [C++], migrating from UNIX
- migration [C++]
- UNIX [C++], porting to Win32
- porting to Win32 [C++], from UNIX
- porting to Win32 [C++]
- Win32 applications [C++], migrating from UNIX
ms.assetid: 3837e4fe-3f96-4f24-b2a1-7be94718a881
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a5dddac6d5e8b5be1b99d9c8004fcaa36d6b0b30
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394037"
---
# <a name="porting-from-unix-to-win32"></a>UNIX から Win32 への移植

アプリケーションを UNIX から Windows に移行するときにいくつかのオプションがあります。  
  
- UNIX のライブラリを使用して UNIX から Win32 にアプリケーションを移植する  
  
- UNIX から Win32 にアプリケーションをネイティブに移植する  
  
- POSIX サブシステムを使用して Windows 上で UNIX アプリケーションを実行する  
  
## <a name="unix-libraries"></a>UNIX ライブラリ  
 
UNIX プログラマが通常検討する 1 つのオプションは、Win32 実行可能ファイルとして UNIX コードをコンパイルできるサードパーティ製の UNIX のようなライブラリを使用することです。 いくつかの商用 (および少なくとも 1 つのパブリック ドメイン) のライブラリがこれを行います。 これは、一部のアプリケーションのためのオプションです。 これらの移植ライブラリの利点は、最初の移植作業を最小限にできることです。 競争力のあるソフトウェア製品にとっての主な短所は、通常アプリケーションのネイティブ Win32 の移植の方が高速で、機能も多くなります。 Win32 呼び出しを行って Windows のパワーを利用する必要がある場合は、アプリケーションが UNIX シェルの外に出ることで不便が生じる可能性があります。  
  
UNIX を Visual C++ に移植してサポートするためのMicrosoft とサード パーティのリソースを次に示します。  
  
### <a name="unix-migration-guides"></a>UNIX 移行ガイド  
[UNIX カスタム アプリケーションの移行ガイド](https://technet.microsoft.com/library/bb656290.aspx)は、UNIX から Win32 環境にコードを移行するときの技術的なサポートを提供します。  
  
[Unix 移行プロジェクト ガイド](https://technet.microsoft.com/library/bb656287.aspx)は、大規模なプロジェクトを UNIX から Win32 に移行する場合の高度なサポートを提供する点で、UNIX カスタム アプリケーション移行ガイドを補足します。 ガイドは、プロジェクトの移行の各段階で考慮する問題へのアドバイスを提供します。
  
### <a name="microsoft-windows-services-for-unix-sfu"></a>Microsoft Windows Services for UNIX (SFU)  
Microsoft Windows Services for UNIX (SFU) は、Windows を既存の UNIX ベースの環境に統合するための幅広いクロス プラットフォーム サービスを提供します。 UNIX 用のサービスは、ファイル共有、リモート アクセスと管理、パスワード同期、一般的なディレクトリの管理、一連の共通ユーティリティ、およびシェルを提供します。  
  
[Windows Services for UNIX](http://www.microsoft.com/downloads/details.aspx?FamilyID=896c9688-601b-44f1-81a4-02878ff11778&displaylang=en)  
  
### <a name="interopsystemscom"></a>InteropSystems.com  
[http://www.interopsystems.com/](http://www.interopsystems.com/)  
  
UNIX から Win32 への移植をサポートするソフトウェアを提供する企業のサードパーティ サイトです。  
  
### <a name="c-boost-web-site"></a>C++ による Web サイトの向上  
[http://boost.sourceforge.net/regression-logs/](http://boost.sourceforge.net/regression-logs/)  
  
[http://boost.sourceforge.net/boost-build2/](http://boost.sourceforge.net/boost-build2/)  
  
## <a name="porting-unix-applications-directly-to-win32"></a>Win32 に UNIX アプリケーションを直接移植する  
 
別のオプションは、Win32 に直接 UNIX アプリケーションを移植することです。 ANSI C と C++ のライブラリ、および商用の C コンパイラのライブラリを使用して、UNIX アプリケーションが使用する従来のシステム呼び出しの多くが Win32 アプリケーションで使用できます。  
  
**stdio** ベースのアプリケーションの出力モデルは、Win32 コンソール API が **stdio** モデルを模倣していて、Win32 コンソールの API を使用する *curses* のバージョンが存在するため、変更する必要がありません。 詳細については、「[SetConsoleCursorPosition](https://msdn.microsoft.com/library/windows/desktop/ms686025)」を参照してください。  
  
Berkeley ソケット ベースのアプリケーションが Win32 アプリケーションとして機能するために、変更はほとんど必要ありません。 Windows ソケット インターフェイスは、WinSock の仕様の序論のセクションで説明されている最小限の変更により、BSD ソケットの移植のために設計されました。  
  
Windows は DCE に準拠した RPC をサポートするので、RPC ベースのアプリケーションは簡単に使用できます。 「[RPC 関数](/windows/desktop/Rpc/rpc-functions)」を参照してください。  
  
最も大きな違いの 1 つが、プロセス モデルにあります。 UNIX には `fork` がありますが、Win32 にはありません。 `fork` とコード ベースの使用法によりますが、Win32 では `CreateProcess` と `CreateThread` の 2 つの API を使用できます。 複数のコピーを fork する UNIX アプリケーションは、複数のプロセス、または複数のスレッド内の 1 つのプロセスのいずれかを持つよう Win32 で書き直すことができます。 複数のプロセスを使用している場合は、プロセス間で通信するため (そしておそらく、`fork` が提供する機能が必要とされる場合は、親のように新しいプロセスのコードとデータを更新するため) に使用できる IPC のメソッドが複数あります。 IPC の詳細については、「[プロセス間通信](/windows/desktop/ipc/interprocess-communications)」を参照してください。  
  
Windows と UNIX のグラフィカルなモデルは、大きく異なります。 UNIX はX Window System GUIを使用し、Windows は GUI を使用します。 概念的に似ていますが、X API と GDI API の単純なマッピングはありません。 ただし、OpenGL のサポートが、UNIX の OpenGL ベースのアプリケーションを移行するのに使用できます。 また、Windows 用の X クライアントと X サーバーもあります。 GDI の詳細については、「[デバイス コンテキスト](https://msdn.microsoft.com/library/windows/desktop/dd183553)」 を参照してください。  
  
多くの CGI アプリケーションを含む基本的な UNIX アプリケーションは、Windows で実行されている Visual C++ に簡単に移植できるはずです。 `open`、`fopen`、`read`、`write` などの関数が、Visual C++ ランタイム ライブラリで利用できます。 また、C UNIX API と Win32 API の間には 1 対 1 のマッピングがあります。`open` は `CreateFile`、`read` は `ReadFile`、`write` は `WriteFile`、`ioctl` は `DeviceIOControl`、`close` は `CloseFile` などのマッピングです。  
  
## <a name="windows-posix-subsystem"></a>Windows の POSIX サブシステム  
 
UNIX プログラマが確認するもう 1 つのオプション は、Windows の POSIX サブシステムです。 ただし、これは Windows NT の作成時に標準化された唯一の POSIX バージョンである POSIX 1003.1 のみサポートします。 それ以降は、ほとんどのアプリケーションは Win32 に変換されたので、このサブシステムを拡張する要求がほとんどありませんでした。 1003.1 システムは全機能を備えたアプリケーションに対しては、多くの機能 (1003.2 にあるもの、ネットワークのサポートなど) が含まれていないため、機能が制限されます。 Windows POSIX サブシステムで動作する、全機能を備えたアプリケーションは、メモリ マップ ファイル、ネットワーク、グラフィックなど、Win32 アプリケーションで利用できる Windows の機能にアクセスしません。 VI、LS、および GREP などのアプリケーションが、Windows POSIX サブシステムの主な対象です。  
  
## <a name="see-also"></a>参照  
 
[Visual C++ 移植とアップグレードのガイド](visual-cpp-change-history-2003-2015.md)<br/>
[UNIX](../c-runtime-library/unix.md)<br/>
[推論規則](../build/inference-rules.md)