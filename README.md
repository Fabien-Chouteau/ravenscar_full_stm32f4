# ravenscar_full_stm32f4
Ravenscar Full run-time for the STM32F407

## Usage

First edit you `alire.toml` file and add the following elements:
 - Add `bare_runtime` in the dependency list:
   ```toml
   [[depends-on]]
   ravenscar_full_stm32f4 = "*"
   ```

Then edit your project file to add the following elements:
 - "with" the run-time project file. With this, gprbuild will compile the run-time before your application
   ```ada
   with "ravenscar_build.gpr";
   ```
 - Specify the `Target` and `Runtime` attributes:
   ```ada
      for Target use "arm-eabi";
      for Runtime ("Ada") use Ravenscar_Build'Runtime ("Ada");
   ```
