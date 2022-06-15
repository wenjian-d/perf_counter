Import('rtconfig')
from building import *
import shutil

src = ['perf_counter.c', 'os/perf_os_patch_rt_thread.c']

cwd = GetCurrentDir()
path = [cwd]
group = []

#delate unused files
try:
    shutil.rmtree(os.path.join(cwd,'.github'))
    shutil.rmtree(os.path.join(cwd,'.vscode'))
    shutil.rmtree(os.path.join(cwd,'CI'))
    shutil.rmtree(os.path.join(cwd,'cmsis-pack'))
    shutil.rmtree(os.path.join(cwd,'lib'))
    shutil.rmtree(os.path.join(cwd,'example'))
    os.remove(os.path.join(cwd,'systick_wrapper_gcc.s'))
    os.remove(os.path.join(cwd,'systick_wrapper_ual.s'))
except:
    pass

group = DefineGroup('perf_counter', src, depend = ['PKG_USING_PERF_COUNTER'], CPPDEFINES = ['__PERF_CNT_USE_RTOS__'], CPPPATH = path)

Return('group')