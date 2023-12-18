创建环境：

    conda create --n rosetta   
    
    #指定python（大项目通常对python版本有要求）
    conda create --name yourEnv python=2.7

删除环境：  

    conda env remove --name myenv 
    

进入环境：

    conda activate rosetta 


查看版本里的所有包:

     conda list  


查看所有环境：  

    conda info --envs ;
